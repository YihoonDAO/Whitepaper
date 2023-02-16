# Quick Start

didao.id reads the records parameter of the URL.

The developer only needs to fill in the specific parameters according to the specification and direct the user to the corresponding links, and then the user can make changes to the user's data once the user is sure.

The general flow is as follows.

```
const records = [{
  action: 'add',
  key: 'profile.website',
  value: 'https://didao.id',
}, {
  action: 'delete',
  key: 'profile.twitter',
}, {
  action: 'replace',
  key: 'profile.avatar',
  value: 'https://data.didao.id/favicon.ico',
}]

const queryString = window.encodeURIComponent(JSON.stringify(records))

window.open(`https://data.didao.id/dasdeveloper.dao?records=${queryString}`)
```

After opening the corresponding link, the user will see a screen similar to the following.&#x20;

&#x20;                                                 <mark style="color:green;">**User interface diagram**</mark>

When the user clicks on the confirmation, the data update operation will be completed.

During this process, the developer does not have to consider the relatively complex in-chain operations at all, and the security of the user's data is not compromised at all.
