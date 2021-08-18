# ProxyShell-POC-Mod
A Proof of Concept for ProxyShell (CVE-2021-34473, CVE-2021-34523, CVE-2021-31207) vulnerability.
This exploit code is a merge of two POC. They both had pros & cons; So I merged them.
Credits to [@donnymaasland](https://twitter.com/donnymaasland) (https://github.com/dmaasland/proxyshell-poc) & [@ber_m1ng](https://twitter.com/ber_m1ng) (https://github.com/ktecv2000/ProxyShell)

## Motivation
I used both the above POC's in my lab. But I had some issues with them.
- [@donnymaasland](https://github.com/dmaasland/proxyshell-poc)'s version had a proxy which gave me back so much delay and errors
- [@ber_m1ng](https://github.com/ktecv2000/ProxyShell)'s version don't use EWS to put payload in Draft, Instead it sent payload via mail to inbox.
- To learn more about `ProxyShell` I decided to merge those codes; And it worked

## What's new?
- `X-Anchormailbox` header for Exchange 2016 support

## Installation
```
git clone https://github.com/aravazhimdr/ProxyShell-POC-Mod.git
cd ProxyShell-POC-Mod
virtualenv -p $(which python3) venv
source venv/bin/activate
pip3 install pypsrp requests
cp wsman.py venv/lib/*/site-packages/pypsrp/wsman.py
```

__Note: This POC uses modified version of wsman.py from [@ber_m1ng](https://github.com/ktecv2000/ProxyShell)__

## Usage
```
python3 proxyshell_mod.py -u exchange-url -e email@lab.local
```

## Credits & Thanks
- [@donnymaasland](https://twitter.com/donnymaasland)
- [@ber_m1ng](https://twitter.com/ber_m1ng)

## Reference
 - https://www.zerodayinitiative.com/blog/2021/8/17/from-pwn2own-2021-a-new-attack-surface-on-microsoft-exchange-proxyshell
 - https://blog.orange.tw/2021/08/proxyshell-a-new-attack-surface-on-ms-exchange-part-3.html
 - https://y4y.space/2021/08/12/my-steps-of-reproducing-proxyshell/
 - https://peterjson.medium.com/reproducing-the-proxyshell-pwn2own-exploit-49743a4ea9a1
 - https://docs.microsoft.com/en-us/powershell/module/exchange/?view=exchange-ps
 - https://docs.microsoft.com/en-us/archive/blogs/webdav_101/best-practices-ews-authentication-and-access-issues
