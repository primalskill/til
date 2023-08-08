# Lookup Server IP

```shell
ifconfig -a
```

If `ifconfig` is not available:

```shell
ip addr
```

The IP addrss is the `inet` or `inet6` property value under the first ethernet interface that is usually `eth0`.

---

#### Refs

- Docs: https://man7.org/linux/man-pages/man8/ifconfig.8.html
