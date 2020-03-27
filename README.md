# snow_inv_plugin
ServiceNow Inventory Plugin


Have you installed the enhanced inventory update set on your instance?

https://snprotips.com/installing-an-update-set-from-xml











# Dependancies

```
$ source /var/lib/awx/venv/ansible/bin/activate
$ umask 0022
$ pip install requests
$ pip install pysnow
```



# Custom Credential:


input config

YAML
```
fields:
  - type: string
    id: username
    label: SN_USERNAME
  - secret: true
    type: string
    id: password
    label: SN_PASSWORD
  - type: string
    id: instance
    label: SN_INSTANCE
 ```
 JSON
 ```
 {
 "fields": [
  {
   "type": "string",
   "id": "username",
   "label": "SN_USERNAME"
  },
  {
   "secret": true,
   "type": "string",
   "id": "password",
   "label": "SN_PASSWORD"
  },
  {
   "type": "string",
   "id": "instance",
   "label": "SN_INSTANCE"
  }
 ]
}
```


 
 injector config
 
 YAML
 ```
 env:
  SN_INSTANCE: '{{instance}}'
  SN_PASSWORD: '{{password}}'
  SN_USERNAME: '{{username}}'
```
JSON
```
{
 "env": {
  "SN_INSTANCE": "{{instance}}",
  "SN_PASSWORD": "{{password}}",
  "SN_USERNAME": "{{username}}"
 }
}
```

