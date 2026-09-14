## Topology

```
CLIENT(.71) -> EDGE(.72) -> ICP PEER(.69) -> ORIGIN(.73)
```

## Requests Used to Prove Topology Is Working

### 1. Request to ICP Peer

The first request is sent directly to the **ICP Peer (`.69`)** from the Client (`.71`).

Its purpose is to make the ICP Peer fetch/cache the object so that the object is available in the peer cache.

```
root@198.18.129.71:~# curl -ik -H "Host:edge.yap.akamai.com" 'https://198.18.129.69/statuscode/file_1k.html?sim200&abc222'
```

### 2. Request to Edge

The second request is sent to the **Edge (`.72`)** from the Client (`.71`).

Its purpose is to verify that the Edge can fetch the already-cached object from the **ICP Peer (`.69`)**.

```
root@198.18.129.71:~# curl -ik -H "Host:edge.yap.akamai.com" 'https://198.18.129.72/statuscode/file_1k.html?sim200&abc222'
```

