# ssdp
linux command line SSDP (DLNA/UPnP) search tool.


This is a stand alone SSDP (Simple Service Discovery Protocol) utiliy for linux bash,
extracted from the upnpx project at : https://github.com/fkuehne/upnpx



## Build & install: 

* make
* sudo make install


## example:
```
ssdp-search -t 5 | grep ACT-Denon
035. usn=uuid:<obfuscated>::urn:schemas-denon-com:device:ACT-Denon:1, type=ACT-Denon, version=1, location=http://<obfuscated>/upnp/desc/aios_device/aios_device.xml
```

```
ssdp-search -j | jq '.result[] | select(.type == "ContentDirectory")'
{
  "id": 8,
  "usn": "uuid:4d696e69-444c-164e-9d41-9c6b0008512a::urn:schemas-upnp-org:service:ContentDirectory:1",
  "type": "ContentDirectory",
  "version": "1",
  "location": "http://192.168.1.20:8200/rootDesc.xml"
}
{
  "id": 12,
  "usn": "uuid:51599fc6-359c-4fe3-bd4c-15ad4b015e83::urn:schemas-upnp-org:service:ContentDirectory:1",
  "type": "ContentDirectory",
  "version": "1",
  "location": "http://192.168.1.23:2869/upnphost/udhisapi.dll?content=uuid:51599fc6-359c-4fe3-bd4c-15ad4b015e83"
}

```

2020, Bruno Keymolen, bruno.keymolen@gmail.com
