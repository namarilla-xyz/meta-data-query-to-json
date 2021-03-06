# EC2 meta-data, output JSON

Code that will query the meta data of an instance within AWS and provide a json formatted output on Go.

```
# setup Go
wget -P /tmp http://go.googlecode.com/files/go1.0.3.linux-amd64.tar.gz
sudo tar -C /usr/local -xzf /tmp/go1.0.3.linux-amd64.tar.gz
export PATH=$PATH:/usr/local/go/bin

# grab the source file
wget https://github.com/namarilla-xyz/meta-data-query-to-json/blob/main/metadata.go

# print meta-data
go run metadata.go
{"ami-id":"ami-aa941e9a","ami-launch-index":"0","block-device-mapping":{"ami":"sda1","ephemeral0":"sda2","root":"/dev/sda1","swap":"sda3"}, …

# pretty print meta-data
go run metadata.go --prettyprint
{
  "ami-id": "ami-aa941e9a",
  "ami-launch-index": "0",
  "block-device-mapping": {
    "ami": "sda1",
    "ephemeral0": "sda2",
    "root": "/dev/sda1",
    "swap": "sda3"
  },
  …
}
```
