# cloudwatch-metric

Script from http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/mon-scripts.html modified to work in no EC2 instances

Before to run the script
```
sudo apt-get update
sudo apt-get install unzip
sudo apt-get install libwww-perl libdatetime-perl
```

Specify your AWS credentials in a credentials file. First, copy the awscreds.template file included with the monitoring scripts to awscreds.conf as follows:

```
cp awscreds.template awscreds.conf
```
Add the following content to this file:

```
AWSAccessKeyId=my-access-key-id
AWSSecretKey=my-secret-access-key
```

Create cronjob
```
*/5 * * * * /opt/aws-scripts-mon/mon-put-instance-data.pl --mem-used --mem-util --mem-avail --disk-space-util --disk-space-avail --disk-path=/ --from-cron
```
