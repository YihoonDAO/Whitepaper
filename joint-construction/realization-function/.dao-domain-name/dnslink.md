# DNSLink

dao account supports IPNS setting and DNSLink, you can refer to the DNSLink tutorial, add \_dnslink resolution record to the DNS of your domain name, and then set the IPNS of your .dao account to your domain name, when you visit the corresponding dao.cc subdomain, the corresponding IPFS content will be presented.

Take .dao account account.dao as an example, first refer to the DNSLink tutorial and add the following DNS resolution record to the domain libp2p.io

```
> my-dns-tool set \
    --type=TXT \
    --ttl=60 \
    --domain=libp2p.io \
    --name=_dnslink \
    --value="dnslink=/ipfs/Qmc2o4ZNtbinEmRF9UGouBYTuiHbtCSShMFRbBY5ZiZDmU"
```

After adding the DNS resolution record, use data.didao.id to set the IPNS value of account.dao to libp2p.io, as follows.

&#x20;                                          ![设置 IPNS](https://docs.did.id/assets/add-ipns-records.85d16435.png)

Once set up, you can visit the dao.cc subdomain corresponding to account.dao.cc to see if the settings have taken effect.

For DNSLink tutorials, usage examples, and FAQs, please see dnslink.io.
