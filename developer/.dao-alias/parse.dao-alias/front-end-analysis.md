# Front-end Analysis

To resolve .dao aliases on the front end, use [das-sdk-jsopen in new window.](../../../joint-construction/promoters.md)

See Integrating [.dao on the front end for more details](../../../joint-construction/promoters.md)

After that, you just need to call the reverseRecord method and pass in the relevant parameters to complete the front-end parsing of the .dao alias.

Example

```
const account = await das.reverseRecord({
  type: 'blockchain',
  key_info: {
    coin_type: '60',
    chain_id: '1',
    key: '0x1d643fac9a463c9d544506006a6348c234da485f'
  }
})

console.assert(account === 'imac.dao')
```

> [Specific parameter values are shown below Parameter details](../../../joint-construction/promoters.md)
