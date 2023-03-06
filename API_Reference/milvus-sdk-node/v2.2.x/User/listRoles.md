# listRoles()

This method lists all roles in Milvus.

## Invocation

```javascript
new milvusClient(MILUVS_ADDRESS).userManager.listRoles();
```

## Parameters

| Parameter | Description                                                                            | Type   |  
| --------- | -------------------------------------------------------------------------------------- | ------ | 
| timeout?  | An optional duration of time in millisecond to allow for the RPC. Default is undefined | Number |

## Example

```javascript
new milvusClient(MILUVS_ADDRESS).userManager.listRoles();
```

## Return