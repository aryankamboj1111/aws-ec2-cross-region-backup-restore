# aws-ec2-cross-region-backup-restore
Cross-region EC2 backup and restore using EBS snapshots, volumes, and Linux mount operations.


AWS EC2 Cross-Region Backup & Restore Using EBS Snapshot

📌 Project Overview
This project demonstrates cross-region backup and restore in AWS using EBS snapshots.
I successfully created files and folders on an EC2 instance in one AWS region and restored the same data on another EC2 instance in a different region using EBS snapshots and volumes.
This simulates a real-world disaster recovery workflow in cloud environments.

🛠️ Services & Tools Used
AWS EC2
AWS EBS (Elastic Block Store)
EBS Snapshots
Linux (Amazon Linux)
SSH
Linux File System & Mount Commands

⚙️ End-to-End Implementation Steps
Launched an EC2 instance in Region A
Created files and folders inside the instance
Created an EBS snapshot of the attached volume
Copied snapshot to another AWS region
Created a new EBS volume from the snapshot in Region X
Launched a new EC2 instance in Region X
Attached the restored volume to the new instance
Mounted the volume and verified original data

💻 Commands Used
Bash
Copy code
# Check block devices
lsblk

# Check filesystem on restored volume
sudo file -s /dev/nvme1n1p1

# Create mount directory
sudo mkdir /mnt/mybackup

# Mount restored volume
sudo mount -o nouuid /dev/nvme1n1p1 /mnt/mybackup

# Navigate inside mounted volume
cd /mnt/mybackup

# Go to original user directory
cd ec2-user

# Go to original folder created on first instance
cd myfolder

# List recovered files
ls

✅ Result
All files and folders created on the first EC2 instance were successfully accessible on the second EC2 instance in a different AWS region.

📚 Key Learnings
How EBS snapshots work as backup mechanisms
Cross-region disaster recovery in AWS

Creating and restoring EBS volumes
Attaching and mounting volumes in Linux
Real-world cloud backup workflow

🎯 Concepts Covered
Cloud Storage
Disaster Recovery
Cross-Region Architecture
Linux File Systems
AWS Infrastructure Management

 Author
Aryan Kamboj
Cloud Enthusiasts 
