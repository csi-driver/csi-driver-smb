## Driver Parameters
> This driver only supports static provisioning, bring your own Samba server before using this driver.
### Storage Class Usage
> get an [example](../deploy/example/storageclass-smb.yaml)

Name | Meaning | Available Value | Mandatory | Default value
--- | --- | --- | --- | ---
source | Samba Server address | `//smb-server-address/sharename` </br>([Azure File](https://docs.microsoft.com/en-us/azure/storage/files/storage-files-introduction) format: `//accountname.file.core.windows.net/filesharename`) | Yes |
createSubDir | create a sub dir for new volume | `true`, `false` | `false` |
nobrl | specifies the mount option "nobrl" to avoid byte range locks being sent to the "cifs/smb" server. Use with caution! Applications which may rely on proper file lockings will experience malfunction or data loss. | `true`, `false` | `false` |
csi.storage.k8s.io/node-stage-secret-name | secret name that stores `username`, `password`(`domain` is optional) | existing secret name |  Yes  |
csi.storage.k8s.io/node-stage-secret-namespace | namespace where the secret is | k8s namespace  |  Yes  |

### PV/PVC Usage
> get an [example](../deploy/example/pv-smb.yaml)

Name | Meaning | Available Value | Mandatory | Default value
--- | --- | --- | --- | ---
volumeAttributes.source | Samba Server address | `//smb-server-address/sharename` </br>([Azure File](https://docs.microsoft.com/en-us/azure/storage/files/storage-files-introduction) format: `//accountname.file.core.windows.net/filesharename`) | Yes |
nodeStageSecretRef.name | secret name that stores `username`, `password`(`domain` is optional) | existing secret name |  Yes  |
nodeStageSecretRef.namespace | namespace where the secret is | k8s namespace  |  Yes  |
