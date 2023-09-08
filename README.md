# rosbag-sharing-community

## How to upload rosbag files

### 1. Install awscli
At first, install awscli command line tool.  
Please see documents.
https://aws.amazon.com/jp/cli/

### 2. Setting AWSCLI Configure
Access Key and Secret Access Key are issued in advance.  
After having the key shared, execute the following command and enter the Access Key and Secret Access Key as instructed.

```bash
awscli configure
```

### 3. Upload rosbag file to Cloud

```bash
aws s3 sync <Rosbag File Path> s3://rosbag-sharing-community/ --endpoint-url=https://s3.us-west-1.wasabisys.com/
```
If you create a new folder and place it there,
```bash
aws s3 sync <Rosbag File Path> s3://rosbag-sharing-community/<New Folder Name>/ --endpoint-url=https://s3.us-west-1.wasabisys.com/
```

### 3. Check uploaded rosbag file
```bash
aws s3 ls s3://rosbag-sharing-community/  --endpoint-url=https://s3.us-west-1.wasabisys.com/
```
If it has been uploaded successfully, the list will be displayed.