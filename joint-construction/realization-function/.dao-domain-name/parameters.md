# Parameters

The records parameter is an array whose contents are each an action for the current .dao account, including the following actions.

add (add)

delete

replace (replace)

Note that the value of the records parameter must be a valid JSON string, escaped by encodeURIComponent.

Depending on the operation, there are different parameter requirements, which are described below.

Add data: add

This will add the corresponding .dao data.

If the same key already exists, the previous key will not be overwritten and both the old and new data will be present.

```
const records = [{
  action: 'add',
  key: 'profile.twitter',
  value: 'dotdao',
  label: 'dotdaoHQ',
  ttl: 300,
}, {
  action: 'add',
  key: 'profile.website',
  value: 'https://didao.id',
}]
```

Delete data: delete

This will delete the corresponding .dao data.

If there are multiple identical keys, all data under the same key will be deleted.

```
const records = [{
  action: 'delete',
  key: 'profile.twitter',
}, {
  action: 'delete',
  key: 'profile.website',
}]
```

Modify data: replace

This will replace the corresponding .dao data.

Since .dao allows multiple identical keys, it is not possible to specify which key parameter is to be modified via the URL parameter. So if you want to modify a key, you do so by replacing it completely. Here, all previous keys are completely replaced by the new key, and if there are multiple identical keys, they will be overwritten by the new data.

```
const records = [{
  action: 'replace',
  key: 'profile.avatar',
  value: 'https://data.didao.id/favicon.ico',
}]
```

Therefore, if you want to modify the data of a key, you need to do so by using the replace operation.
