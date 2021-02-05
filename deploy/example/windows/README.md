# CSI Driver on Windows

## Feature Status: Beta
Refer to [Windows-CSI-Support](https://github.com/kubernetes/enhancements/tree/master/keps/sig-windows/1122-windows-csi-support) for more details.

## Prerequisite
- [Install CSI-Proxy on Windows Node](https://github.com/Azure/aks-engine/blob/master/docs/topics/csi-proxy-windows.md)

## Deploy a Windows pod with PVC mount
### Create a Windows deployment
```
kubectl apply -f https://raw.githubusercontent.com/kubernetes-csi/csi-driver-smb/master/deploy/example/windows/statefulset.yaml
```

### Enter pod container to verify
```
$ kubectl exec -it busybox-smb-0  -- bash
C:/ $ ls mnt/smb
```

In the above example, there is a `c:\mnt\smb` directory mounted as SMB filesystem.
