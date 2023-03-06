# dropRole()

This method drops a user role in Milvus.

## Invocation

```javascript
new milvusClient(MILUVS_ADDRESS).userManager.dropRole(DropUserReq);
```

## Parameters

### DropUserReq

| Parameter | Description                                                                            | Type   |
| --------- | -------------------------------------------------------------------------------------- | ------ |
| roleName  | The role name                                                                          | String |
| timeout?  | An optional duration of time in millisecond to allow for the RPC. Default is undefined | Number |

## Example

```javascript
new milvusClient(MILUVS_ADDRESS).userManager.dropRole({
  roleName: "my-milvus-role",
});
```

## Return

```javascript
{ error_code: 'Success', reason: '' }
```