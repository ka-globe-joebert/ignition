# ignition

## quickstart
```
wget https://github.com/coreos/fcct/releases/download/v0.7.0/fcct-x86_64-unknown-linux-gnu
sudo mv fcct-x86_64-unknown-linux-gnu /usr/local/bin/fcct
chmod +x /usr/local/bin/fcct
fcct -s -p -o provision.ign provision.fcc
aws ec2 run-instances --image-id ami-0803382b99fe04f3c --instance-type t2.micro --key-name joebert --security-group-ids sg-085f3f3bf56ec6401 --user-data file://provision.ign
aws ec2 request-spot-instances --spot-price "0.01" --instance-count 1 --type "one-time" --launch-specification file://specification.json
```
