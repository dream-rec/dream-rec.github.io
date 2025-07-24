### Vmess
`vmess://ewogICJ2IjogIjIiLAogICJwcyI6ICJhd3MyfGhNMTAubG92ZUB4cmF5LmNvbSIsCiAgImFkZCI6ICIzLjE0NC40NC4yMSIsCiAgInBvcnQiOiAzNjA4NiwKICAiaWQiOiAiOTQ1Mzg1YTgtZjI5Yy00NjVkLWI5MWMtMWQ1ZDJlMjA4YTFjIiwKICAiYWlkIjogMCwKICAibmV0IjogIndzIiwKICAidHlwZSI6ICJub25lIiwKICAiaG9zdCI6ICIiLAogICJwYXRoIjogIi85NDUzODVhOC1mMjljLTQ2NWQtYjkxYy0xZDVkMmUyMDhhMWMiLAogICJ0bHMiOiAibm9uZSIKfQ==`
### Vless
`vless://6d82e7f5-19ed-4a1e-d9ff-0b9b589015ef@3.144.44.21:24162?type=ws&security=none&path=%2F6d82e7f5-19ed-4a1e-d9ff-0b9b589015ef#aws1|03Du.love@xray.com`
### CF-node
**v2ray-CF WORKER**
`vless://b183110c-5b46-4884-aa11-ec49354eab66@myvless-work.lmx450028818.workers.dev:443?encryption=none&security=tls&sni=myvless-work.lmx450028818.workers.dev&fp=randomized&type=ws&host=myvless-work.lmx450028818.workers.dev&path=%2F%3Fed%3D2048#myvless-work.lmx450028818.workers.dev`
**clash-meta**
```
- type: vless
  name: myvless-work.lmx450028818.workers.dev
  server: myvless-work.lmx450028818.workers.dev
  port: 443
  uuid: b183110c-5b46-4884-aa11-ec49354eab66
  network: ws
  tls: true
  udp: false
  sni: myvless-work.lmx450028818.workers.dev
  client-fingerprint: chrome
  ws-opts:
    path: "/?ed=2048"
    headers:
      host: myvless-work.lmx450028818.workers.dev
```


### Link
_**clash 分两种内核，一种meta原生支持vless，另外一种premium，不支持vless，且yaml语法有更改，互不兼容。
两种方式：更改内核或者下载clash verge。**_
**Clash(clash for windows默认是premium内核，只适用于meta内核)**
**Clash-vless**

- 短链：https://dreammx.dpdns.org/c/SijWx0q
- 长链-1 M内核：https://dreammx.dpdns.org/clash?config=vless%3A%2F%2F6d82e7f5-19ed-4a1e-d9ff-0b9b589015ef%403.144.44.21%3A24162%3Ftype%3Dws%26security%3Dnone%26path%3D%252F6d82e7f5-19ed-4a1e-d9ff-0b9b589015ef%23aws1%7C03Du.love%40xray.com&ua=&selectedRules=%5B%5D&customRules=%5B%5D
- 长链-2 P内核：https://lmxxx.dpdns.org/sub?target=clash&url=vmess%3A%2F%2FewogICJ2IjogIjIiLAogICJwcyI6ICJhd3MyfGhNMTAubG92ZUB4cmF5LmNvbSIsCiAgImFkZCI6ICIzLjE0NC40NC4yMSIsCiAgInBvcnQiOiAzNjA4NiwKICAiaWQiOiAiOTQ1Mzg1YTgtZjI5Yy00NjVkLWI5MWMtMWQ1ZDJlMjA4YTFjIiwKICAiYWlkIjogMCwKICAibmV0IjogIndzIiwKICAidHlwZSI6ICJub25lIiwKICAiaG9zdCI6ICIiLAogICJwYXRoIjogIi85NDUzODVhOC1mMjljLTQ2NWQtYjkxYy0xZDVkMmUyMDhhMWMiLAogICJ0bHMiOiAibm9uZSIKfQ%3D%3D&insert=false

 **Quantumult X**

- https://lmxxx.dpdns.org/sub?target=quanx&url=vmess%3A%2F%2FewogICJ2IjogIjIiLAogICJwcyI6ICJhd3MyfEdweWEubG92ZUB4cmF5LmNvbSIsCiAgImFkZCI6ICIzLjE0NC40NC4yMSIsCiAgInBvcnQiOiAyNjcxMSwKICAiaWQiOiAiNGJjZjVkMjYtYzgwZS00NDc0LTgxNWUtZDIzOThmYzhiODc4IiwKICAiYWlkIjogMCwKICAibmV0IjogIndzIiwKICAidHlwZSI6ICJub25lIiwKICAiaG9zdCI6ICIiLAogICJwYXRoIjogIi80YmNmNWQyNi1jODBlLTQ0NzQtODE1ZS1kMjM5OGZjOGI4NzgiLAogICJ0bHMiOiAibm9uZSIKfQ%3D%3D&insert=false

**Quantumult**

- https://lmxxx.dpdns.org/sub?target=quan&url=vmess%3A%2F%2FewogICJ2IjogIjIiLAogICJwcyI6ICJhd3MyfEdweWEubG92ZUB4cmF5LmNvbSIsCiAgImFkZCI6ICIzLjE0NC40NC4yMSIsCiAgInBvcnQiOiAyNjcxMSwKICAiaWQiOiAiNGJjZjVkMjYtYzgwZS00NDc0LTgxNWUtZDIzOThmYzhiODc4IiwKICAiYWlkIjogMCwKICAibmV0IjogIndzIiwKICAidHlwZSI6ICJub25lIiwKICAiaG9zdCI6ICIiLAogICJwYXRoIjogIi80YmNmNWQyNi1jODBlLTQ0NzQtODE1ZS1kMjM5OGZjOGI4NzgiLAogICJ0bHMiOiAibm9uZSIKfQ%3D%3D&insert=false

**Shawdowrocket-vmess**

- https://dreammx.dpdns.org/c/kXIcBLg