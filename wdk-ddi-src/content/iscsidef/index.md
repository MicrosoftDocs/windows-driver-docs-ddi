---
UID: NA:iscsidef
ms.assetid: 39aa6161-feb2-3ec8-a07b-b4e1594d4617
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Iscsidef.h header



This header is used by Storage. For more information, see
- [Storage](../_storage/index.md)

Iscsidef.h contain these programming interfaces:


## Structures

| Title   | Description   |
| ---- |:---- |
| [_ISCSI_IP_Address structure](ns-iscsidef-_iscsi_ip_address.md) | The ISCSI_IP_Address structure defines an IP address. |
| [_ISCSI_LUNList structure](ns-iscsidef-_iscsi_lunlist.md) | The ISCSI_LUNList structure defines a mapping between the LUN number that is used by the operating system and the LUN number that is configured in the iSCSI target. |
| [_ISCSI_LoginOptions structure](ns-iscsidef-_iscsi_loginoptions.md) | The ISCSI_LoginOptions structure defines the characteristics of a logon session. The LoginToTarget_IN routines use these defined characteristics while it logs into an iSCSI target. |
| [_ISCSI_TargetMapping structure](ns-iscsidef-_iscsi_targetmapping.md) | The ISCSI_TargetMapping structure maps a collection of logical unit numbers (LUNs) that are locally defined to a group of 64-bit iSCSI logical unit numbers. |
| [_ISCSI_TargetPortal structure](ns-iscsidef-_iscsi_targetportal.md) | The ISCSI_TargetPortal structure provides a definition of a target portal. |
| [_ISCSI_TargetPortalGroup structure](ns-iscsidef-_iscsi_targetportalgroup.md) | The ISCSI_TargetPortalGroup structure provides a definition of a target portal group. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [*PISCSIIPADDRESSTYPE enumeration](ne-iscsidef-piscsiipaddresstype.md) | The ISCSIIPADDRESSTYPE enumeration indicates formats for an IP address. |
| [*PISCSI_AUTH_TYPES enumeration](ne-iscsidef-piscsi_auth_types.md) | The ISCSI_AUTH_TYPES enumeration indicates the type of authentication method that is used to establish a logon connection. |
| [*PISCSI_DIGEST_TYPES enumeration](ne-iscsidef-piscsi_digest_types.md) | The ISCSI_DIGEST_TYPES enumeration indicates the digest type. |
