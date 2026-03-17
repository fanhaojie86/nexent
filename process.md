# 登录

## url
POST /service/session

## header
```json
{
  "Accept": "application/json;version=8.1;charset=UTF-8",
  "X-Auth-User": "",
  "X-Auth-Key": "",
  "X-Auth-UserType": 2,
  "X-ENCRYPT-ALGORITHM": 1
}
```

## response
需登录获取 X-Auth-Token
```json
{
  "X-Auth-Token": ""
}
```

---
# site

## url
GET /service/sites

## header
```json
{
  "Accept": "application/json;version=8.1;charset=UTF-8",
  "X-Auth-User": "",
  "X-Auth-Key": "",
  "X-Auth-UserType": 2,
  "X-ENCRYPT-ALGORITHM": 1,
  "X-Auth-Token": ""
}
```

## response

---
# 查询模版ID

## url
GET /service/sites/<site_id>/vms

---
# 查询虚拟机模版信息

## url
GET /service/sites/<site_id>/vms/<vm_id>

## response

---
# 基于模版创建虚拟机

## url
POST /service/sites/<site_id>/vms/<vm_id>/action/clone

## header
```json
{
  "Accept": "application/json;version=8.1;charset=UTF-8",
  "X-Auth-User": "",
  "X-Auth-Key": "",
  "X-Auth-UserType": 2,
  "X-ENCRYPT-ALGORITHM": 1,
  "X-Auth-Token": ""
}
```

## body
```json
{
  "name": "",
  "description": "",
  "vmConfig": {
    "cpu": {
      "quantity": 4,
      "cpuHotPlug": 1,
      "cpuThreadPolicy": "prefer",
      "cpuPolicy": "shared",
      "cpuBindType": "nobind"
    },
    "memory": {
      "quantityMB": 8192,
      "memHotPlug": 1
    },
    "disks": [
      {
        "datastoreUrn": "",
        "sequenceNum": 1,
        "quantityGB": 100,
        "isDataCopy": true,
        "type": "normal"
      }
    ],
    "properties": {
      "recoverByHost": true
    }
  },
  "osOptions": {
    "osType": "Linux",
    "osVersion": "10088",
    "guestOSName": ""
  },
  "autoBoot": true,
  "isLinkClone": false,
  "vmCustomization": {
    "hostname": "",
    "osType": "Linux",
    "nicSpecification": {
      "ip": "",
      "gateway": "",
      "netmask": "",
      "sequenceNum": 1,
      "ipVersion": 4
    }
  }
}
```

## response