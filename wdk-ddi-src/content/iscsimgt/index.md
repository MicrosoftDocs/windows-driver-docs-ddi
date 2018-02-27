---
UID: NA:iscsimgt
ms.assetid: 0b754abf-ab99-3c3d-989c-a58cb88854c3
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Iscsimgt.h header



This header is used by Storage. For more information, see
- [Storage](../_storage/index.md)

Iscsimgt.h contain these programming interfaces:


## Structures

| Title   | Description   |
| ---- |:---- |
| [_ISCSI_ConnectionStaticInfo structure](ns-iscsimgt-_iscsi_connectionstaticinfo.md) | The ISCSI_ConnectionStaticInfo structure contains information about the characteristics of an established connection. |
| [_ISCSI_Path structure](ns-iscsimgt-_iscsi_path.md) | The ISCSI_Path structure contains information about a connection of the iSCSI portal. |
| [_ISCSI_PortalInfo structure](ns-iscsimgt-_iscsi_portalinfo.md) | The ISCSI_PortalInfo structure contains information about an iSCSI portal. |
| [_ISCSI_RedirectPortalInfo structure](ns-iscsimgt-_iscsi_redirectportalinfo.md) | This ISCSI_RedirectPortalInfo structure contains information about a collection of iSCSI portals that can be used during portal hopping or portal redirect operations. |
| [_ISCSI_RedirectSessionInfo structure](ns-iscsimgt-_iscsi_redirectsessioninfo.md) | This ISCSI_RedirectSessionInfo structure contains information about an iSCSI session and its portal information resulted from iSCSI target redirection. |
| [_ISCSI_SessionStaticInfo structure](ns-iscsimgt-_iscsi_sessionstaticinfo.md) | The ISCSI_SessionStaticInfo structure provides information about the characteristics of an iSCSI session. |
| [_ISCSI_Supported_LB_Policies structure](ns-iscsimgt-_iscsi_supported_lb_policies.md) | The ISCSI_Supported_LB_Policies structure contains information about load balancing policies for multiple connections per session (MCS). |
| [_MSiSCSI_Eventlog structure](ns-iscsimgt-_msiscsi_eventlog.md) | This MSiSCSI_EventLog method is used to log any messages to the event log. |
| [_MSiSCSI_HBAInformation structure](ns-iscsimgt-_msiscsi_hbainformation.md) | The MSiSCSI_HBAInformation structure is used by storage miniport drivers to report information about the host bus adapters (HBAs) that they manage to the iSCSI initiator service. |
| [_MSiSCSI_HBASessionConfig structure](ns-iscsimgt-_msiscsi_hbasessionconfig.md) | The MSiSCSI_HBASessionConfig structure contains the default logon characteristics that a particular instance of a storage miniport driver uses to create a logon session with a target device. |
| [_MSiSCSI_InitiatorInstanceFailureEvent structure](ns-iscsimgt-_msiscsi_initiatorinstancefailureevent.md) | The MSiSCSI_InitiatorInstanceFailureEvent structure is used to report an event when an initiator instance failure occurs. |
| [_MSiSCSI_InitiatorNodeFailureEvent structure](ns-iscsimgt-_msiscsi_initiatornodefailureevent.md) | The MSiSCSI_InitiatorNodeFailureEvent structure is used to report an event when a node failure occurs. |
| [_MSiSCSI_InitiatorSessionInfo structure](ns-iscsimgt-_msiscsi_initiatorsessioninfo.md) | The MSiSCSI_InitiatorSessionInfo structure contains information about a collection of sessions that belong to the indicated HBA initiator. |
| [_MSiSCSI_PortalInfoClass structure](ns-iscsimgt-_msiscsi_portalinfoclass.md) | The MSiSCSI_PortalInfoClass structure contains information about a collection of iSCSI portals. |
| [_MSiSCSI_QueryLBPolicy structure](ns-iscsimgt-_msiscsi_querylbpolicy.md) | This MSiSCSI_QueryLBPolicy method returns the MCS load balancing policy for each information if any that has been set across different iSCSI session. |
| [_MSiSCSI_RedirectPortalInfoClass structure](ns-iscsimgt-_msiscsi_redirectportalinfoclass.md) | The MSiSCSI_RedirectPortalInfoClass structure contains information about a collection of sessions for an adapter ID. It also contains the portal redirection information for each of the sessions. |
| [_PingIPAddress_IN structure](ns-iscsimgt-_pingipaddress_in.md) | The PingIPAddress_IN structure holds the input data for the PingIPAddress method. |
| [_PingIPAddress_OUT structure](ns-iscsimgt-_pingipaddress_out.md) | The PingIPAddress_OUT structure holds the output data for the PingIPAddress method. |
| [_SetLoadBalancePolicy_IN structure](ns-iscsimgt-_setloadbalancepolicy_in.md) | The SetLoadBalancePolicy_IN structure holds the input data for the SetLoadBalance method. |
| [_SetLoadBalancePolicy_OUT structure](ns-iscsimgt-_setloadbalancepolicy_out.md) | The SetLoadBalancePolicy_OUT structure holds the output data for the SetLoadBalance method. |
