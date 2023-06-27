# [AWS EC2 Setup](https://console.aws.amazon.com)

Creating an instance from the command line:
```bash
while ! aws --profile (profile-name) ec2 run-instances --image-id (ami-xxx) --count 1 --instance-type p4de.24xlarge --key-name (key-name) --security-group-ids (sg-xxx) --submet-id (subnet-xxx) --block-device-mappings "DeviceName=/dev/sdf, Ebs={DeleteOnTermination=true, Iops=3000, VolumeSize=1000, VolumeType=gp3, Encrypted=false}" ; do echo "..."; sleep 30; done;
```

EBS Setup
1. Create and attach EBS volume through AWS Console online.
2. `lsblk` to identify name of EBS volume.
3. Format the EBS volume.
```bash
sudo mkfs -t ext4 /dev/{volume-name}
```
4. Create a mount point (This is where your new data will live.) We use `/data` here but this can be changed to anything.
```bash
sudo mount /dev/{volume-name} /data
```
5. Create symlinks:
```bash
mv /home/ubuntu/.cache /data/
ln -s /data/.cache /home/ubuntu/.cache
```
In general, `ln -s (where-data-should-be) (symlink-entry-point)`. Other paths to symlink: `anaconda3`.