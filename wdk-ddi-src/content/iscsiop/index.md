---
UID: NA:iscsiop
ms.assetid: 16203758-f031-3557-a36d-abe33c7c4a6d
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Iscsiop.h header



This header is used by Storage. For more information, see
- [Storage](../_storage/index.md)

Iscsiop.h contain these programming interfaces:


## Structures

| Title   | Description   |
| ---- |:---- |
| [_AddConnectionToSession_IN structure](ns-iscsiop-_addconnectiontosession_in.md) | The AddConnectionToSession_IN structure holds input data for the AddConnectionToSession method, which is used to add a new connection to an already existing session. |
| [_AddConnectionToSession_OUT structure](ns-iscsiop-_addconnectiontosession_out.md) | The AddConnectionToSession_OUT structure holds output data for the AddConnectionToSession method. |
| [_AddRADIUSServer_IN structure](ns-iscsiop-_addradiusserver_in.md) | The AddRADIUSServer_IN structure holds the input data for the AddRADIUSServer method, which is used to add a new RADIUS server entry to existing list. |
| [_AddRADIUSServer_OUT structure](ns-iscsiop-_addradiusserver_out.md) | The AddRADIUSServer_OUT structure holds the output data for the AddRADIUSServer method. |
| [_AddiSNSServer_IN structure](ns-iscsiop-_addisnsserver_in.md) | The AddiSNSServer_IN structure holds the input data for the user-mode AddISNSServer method, which is used to add a new iSNS server entry to the list of iSNS server names that the initiator maintains. |
| [_AddiSNSServer_OUT structure](ns-iscsiop-_addisnsserver_out.md) | The AddiSNSServer_OUT structure holds the output data for the user-mode AddISNSServer method. |
| [_ClearCache_OUT structure](ns-iscsiop-_clearcache_out.md) | The ClearCache_OUT structure holds the output data for the ClearCache method. |
| [_DeleteInitiatorNodeName_IN structure](ns-iscsiop-_deleteinitiatornodename_in.md) | The DeleteInitiatorNodeName_IN structure holds the input data for the DeleteInitiatorNodeName method, which is used to delete an initiator node name. |
| [_DeleteInitiatorNodeName_OUT structure](ns-iscsiop-_deleteinitiatornodename_out.md) | The DeleteInitiatorNodeName_OUT structure holds the output data for the DeleteInitiatorNodeName method. |
| [_GetPresharedKeyForId_IN structure](ns-iscsiop-_getpresharedkeyforid_in.md) | The GetPresharedKeyForId_IN structure holds the input data for the GetPresharedKeyForId method. |
| [_GetPresharedKeyForId_OUT structure](ns-iscsiop-_getpresharedkeyforid_out.md) | The GetPresharedKeyForId_OUT structure holds the output data for the GetPresharedKeyForId method. |
| [_ISCSI_Persistent_Login structure](ns-iscsiop-_iscsi_persistent_login.md) | The ISCSI_Persistent_Login structure defines a persistent logon that the operating system initiates automatically when the computer boots up. |
| [_LoginToTarget_IN structure](ns-iscsiop-_logintotarget_in.md) | The LoginToTarget_IN structure holds the input data for the LoginToTarget method, which is used to login to a target. |
| [_LoginToTarget_OUT structure](ns-iscsiop-_logintotarget_out.md) | The LoginToTarget_OUT structure holds the output data for the LoginToTarget method. |
| [_LogoutFromTarget_IN structure](ns-iscsiop-_logoutfromtarget_in.md) | The LogoutFromTarget_IN structure holds the input data for the LogoutFromTarget method, which is used to log out from an iSCSI target. |
| [_LogoutFromTarget_OUT structure](ns-iscsiop-_logoutfromtarget_out.md) | The LogoutFromTarget_OUT structure holds the output data for the LogoutFromTarget method. |
| [_MSiSCSI_AdapterEvent structure](ns-iscsiop-_msiscsi_adapterevent.md) | The MSiSCSI_AdapterEvent structure contains information that is reported whenever an adapter event occurs. |
| [_MSiSCSI_BootInformation structure](ns-iscsiop-_msiscsi_bootinformation.md) | The MSiSCSI_BootInformation structure is used with the MSiSCSI_BootInformation WMI Class to expose information about the node that contains the target boot device. |
| [_MSiSCSI_LUNMappingInformation structure](ns-iscsiop-_msiscsi_lunmappinginformation.md) | This MSiSCSI_LUNMappingInformation structure provides the SCSI address information that the operating system assigns to a particular logical unit. |
| [_MSiSCSI_PersistentLogins structure](ns-iscsiop-_msiscsi_persistentlogins.md) | The MSiSCSI_PersistentLogins structure contains the list of persistent target logon sessions. |
| [_MSiSCSI_TargetMappings structure](ns-iscsiop-_msiscsi_targetmappings.md) | The MSiSCSI_TargetMappings structure contains a set of logical unit number (LUN) mappings that are associated with an initiator instance. |
| [_RemoveConnectionFromSession_IN structure](ns-iscsiop-_removeconnectionfromsession_in.md) | The RemoveConnectionFromSession_IN structure holds the input data for the RemoveConnectionFromSession method, which is used to remove a connection from a session. |
| [_RemoveConnectionFromSession_OUT structure](ns-iscsiop-_removeconnectionfromsession_out.md) | The RemoveConnectionFromSession_OUT structure holds the output data for the RemoveConnectionFromSession method, which is used to remove a connection from a session. |
| [_RemovePersistentLogin_IN structure](ns-iscsiop-_removepersistentlogin_in.md) | The RemovePersistentLogin_IN structure holds the input data for the RemovePersistentLogin method, which is used to remove persistent login information. |
| [_RemovePersistentLogin_OUT structure](ns-iscsiop-_removepersistentlogin_out.md) | The RemovePersistentLogin_OUT structure holds the output data for the RemovePersistentLogin method. |
| [_RemoveRADIUSServer_IN structure](ns-iscsiop-_removeradiusserver_in.md) | The RemoveRADIUSServer_IN structure holds the input data for the user-mode RemoveRADIUSServer method, which is used to remove a RADIUS server entry. |
| [_RemoveRADIUSServer_OUT structure](ns-iscsiop-_removeradiusserver_out.md) | The RemoveiSNSServer_OUT structure holds the output data for the RemoveRADIUSServer method. |
| [_RemoveiSNSServer_IN structure](ns-iscsiop-_removeisnsserver_in.md) | The RemoveiSNSServer_IN structure holds the input data for the user-mode RemoveISNSServer method, which is used to remove an iSNS server entry. |
| [_RemoveiSNSServer_OUT structure](ns-iscsiop-_removeisnsserver_out.md) | The RemoveiSNSServer_OUT structure holds the output data for the user-mode RemoveISNSServer method. |
| [_ScsiInquiry_IN structure](ns-iscsiop-_scsiinquiry_in.md) | The ScsiInquiry_IN structure holds the input data for the ScsiInquiry method, which is used to send a SCSI inquiry command. |
| [_ScsiInquiry_OUT structure](ns-iscsiop-_scsiinquiry_out.md) | The ScsiInquiry_OUT structure holds the output data for the ScsiInquiry method. |
| [_ScsiReadCapacity_IN structure](ns-iscsiop-_scsireadcapacity_in.md) | The ScsiReadCapacity_IN structure holds the input data for the ScsiReadCapacity method, which is used to send a SCSI read Ccapacity command. |
| [_ScsiReadCapacity_OUT structure](ns-iscsiop-_scsireadcapacity_out.md) | The ScsiReadCapacity_OUT structure holds the output data for the ScsiReadCapacity method. |
| [_ScsiReportLuns_IN structure](ns-iscsiop-_scsireportluns_in.md) | The ScsiReportLuns_IN structure holds the input data for the ScsiReportLuns method. |
| [_ScsiReportLuns_OUT structure](ns-iscsiop-_scsireportluns_out.md) | The ScsiReportLuns_OUT structure holds the output data for the ScsiReportLuns method. |
| [_SendTargets_IN structure](ns-iscsiop-_sendtargets_in.md) | The SendTargets_IN structure holds the input data for the SendTargets method. |
| [_SendTargets_OUT structure](ns-iscsiop-_sendtargets_out.md) | The SendTargets_OUT structure holds the output data for the SendTargets method. |
| [_SetCHAPSharedSecret_IN structure](ns-iscsiop-_setchapsharedsecret_in.md) | The SetCHAPSharedSecret_IN structure holds the input data for the SetCHAPSharedSecret method. |
| [_SetCHAPSharedSecret_OUT structure](ns-iscsiop-_setchapsharedsecret_out.md) | The SetCHAPSharedSecret_OUT structure holds the output data for the SetCHAPSharedSecret method. |
| [_SetGenerationalGuid_IN structure](ns-iscsiop-_setgenerationalguid_in.md) | The SetGenerationalGuid_IN structure holds the input data for the SetGenerationalGuid method. |
| [_SetGenerationalGuid_OUT structure](ns-iscsiop-_setgenerationalguid_out.md) | The SetGenerationalGuid_OUT structure holds the output data for the SetGenerationalGuid method. |
| [_SetGroupPresharedKey_IN structure](ns-iscsiop-_setgrouppresharedkey_in.md) | The SetGroupPresharedKey_IN structure holds the input data for the SetGroupPresharedKey method. |
| [_SetGroupPresharedKey_OUT structure](ns-iscsiop-_setgrouppresharedkey_out.md) | The SetGroupPresharedKey_OUT structure holds the output data for the SetGroupPresharedKey method. |
| [_SetInitiatorNodeName_IN structure](ns-iscsiop-_setinitiatornodename_in.md) | The SetInitiatorNodeName_IN structure holds the input data for the SetInitiatorNodeName method. |
| [_SetInitiatorNodeName_OUT structure](ns-iscsiop-_setinitiatornodename_out.md) | The SetInitiatorNodeName_OUT structure holds the output data for the SetInitiatorNodeName method. |
| [_SetPresharedKeyForId_IN structure](ns-iscsiop-_setpresharedkeyforid_in.md) | The SetPresharedKeyForId_IN structure holds the input data for the SetPresharedKeyForId method. |
| [_SetPresharedKeyForId_OUT structure](ns-iscsiop-_setpresharedkeyforid_out.md) | The SetPresharedKeyForId_OUT structure holds the output data for the SetPresharedKeyForId method. |
| [_SetRADIUSSharedSecret_IN structure](ns-iscsiop-_setradiussharedsecret_in.md) | The SetRADIUSSharedSecret_IN structure holds the input data for the SetRADIUSSharedSecret method. |
| [_SetRADIUSSharedSecret_OUT structure](ns-iscsiop-_setradiussharedsecret_out.md) | The SetRADIUSSharedSecret_OUT structure holds the output data for the SetRADIUSSharedSecret method. |
| [_SetTunnelModeOuterAddress_IN structure](ns-iscsiop-_settunnelmodeouteraddress_in.md) | The SetTunnelModeOuterAddress_IN structure holds the input data for the SetTunnelModeOuterAddress method. |
| [_SetTunnelModeOuterAddress_OUT structure](ns-iscsiop-_settunnelmodeouteraddress_out.md) | The SetTunnelModeOuterAddress_OUT structure holds the output data for the SetTunnelModeOuterAddress method. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [*PISCSI_ADAPTER_EVENT_CODE enumeration](ne-iscsiop-piscsi_adapter_event_code.md) | The ISCSI_ADAPTER_EVENT_CODE enumeration indicates the type of adapter event. |
| [*PLOGINSESSIONTYPE enumeration](ne-iscsiop-ploginsessiontype.md) | The LOGINSESSIONTYPE enumeration indicates the type of logon session. |
