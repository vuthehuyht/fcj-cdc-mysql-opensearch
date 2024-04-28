---
title : "Deploy Python code in EC2"
date :  "`r Sys.Date()`" 
weight: 1
chapter: false
pre: "<b> 3.1 </b>"
---

Make sure that, **MobaXterm** is installed on your local machine. If not installed, visit [link](https://mobaxterm.mobatek.net/) to set up.

Run **MobaXterm**, choose **Session** -> **SSH**
- **Remote host**:  Enter public IP of EC2 created in [2.4](/2-prepare/2.4-createec2/)
- Tick **Specify username** và enter **ubuntu**
- Choose **Advance SSH Settings**, tick **Use private key** and path of pem file downloaded in [2.4](/2-prepare/2.4-createec2/)
![2.4-step-1](/images/deploy-1.png)

Install **python 3.12** and **pip** by running the following commands
```
sudo apt install software-properties-common -y
sudo add-apt-repository ppa:deadsnakes/ppa
sudo apt udpate
sudo apt install python3.12 python3-pip -y
```

Touch **listener.py** file by `vim listener.py` command, the paste the following code and press combination **ESC** -> **:wq!** -> **Enter**
```
import boto3
import json
from pymysqlreplication import BinLogStreamReader
from pymysqlreplication.row_event import (
    DeleteRowsEvent,
    UpdateRowsEvent,
    WriteRowsEvent,
)

def main():
    kinesis = boto3.client("kinesis",region_name="ap-southeast-1")
    
    MYSQL_SETTINGS = {
      "host": "<database endpoint>",
      "port": "<database port>",
      "user": "<database username>",
      "passwd": "database password" 
      }
    '''
    * server_id is your slave identifier, it should be unique.
    * set blocking to True if you want to block and wait for the next event at
    the end of the stream
    * only_events will listen only to describes events 
    '''
    print(">>>listener start streaming to:cdc-data-stream")
    stream = BinLogStreamReader(connection_settings=MYSQL_SETTINGS,
                                server_id=100,
                                blocking=True,
                                resume_stream=True,
                                only_events=[DeleteRowsEvent, WriteRowsEvent, UpdateRowsEvent])
    for binlogevent in stream:
        for row in binlogevent.rows:
            print(">>> start event")
            event = {"schema": binlogevent.schema,
                    "table": binlogevent.table,
                    "type": type(binlogevent).__name__,
                    "row": row
                    }
            print(">>>event",event)
            output = kinesis.put_record(StreamName="<stream name>", Data=json.dumps(event), PartitionKey="default")
            print(">>kinasis output",output)
    stream.close()


if __name__ == "__main__":
    main()
```

Update RDS information and Kinesis created in step [2.2](/2-prepare/2.2-createrds/) and [2.5](/2-prepare/2.5-createkinesisdatastream/)

Touch file to save these dependencies by `vim requirements.txt` and paste content into file
```
requests
boto3
mysql-replication
```

Install these dependencies by `pip install -r requirements.txt` command

Then, let's run a test to see if the code has run successfully by `python3 listener.py` command

The result as image is code running successufully
![2.4-step-1](/images/deploy-2.png)

