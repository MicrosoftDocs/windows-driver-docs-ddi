---
UID: NA:bthxddi
ms.assetid: 0a994ed6-3895-30e7-82d4-1cf07ba8d74d
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Bthxddi.h header



This header is used by Bluetooth. For more information, see
- [Bluetooth](../_bltooth/index.md)

Bthxddi.h contain these programming interfaces:


## Structures

| Title   | Description   |
| ---- |:---- |
| [_BTHX_CAPABILITIES structure](ns-bthxddi-_bthx_capabilities.md) | The BTHX_CAPABILITIES structure describes the capabilities of the Bluetooth Extensible Transport Driver. |
| [_BTHX_HCI_READ_WRITE_CONTEXT structure](ns-bthxddi-_bthx_hci_read_write_context.md) | The BTHX_HCI_READ_WRITE_CONTEXT structure is used as an input/output structure for the IOCTL_BTHX_READ_HCI and IOCTL_BTHX_WRITE_HCI IOCTLs. |
| [_BTHX_VERSION structure](ns-bthxddi-_bthx_version.md) | The BTHX_VERSION structure describes the version or versions that the transport driver supports. |

## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_BTHX_GET_VERSION IOCTL](ni-bthxddi-ioctl_bthx_get_version.md) | Profile drivers use IOCTL_BTHX_GET_VERSION to get the version supported by the transport driver. |
| [IOCTL_BTHX_QUERY_CAPABILITIES IOCTL](ni-bthxddi-ioctl_bthx_query_capabilities.md) | IOCTL_BTHX_QUERY_CAPABILITIES is used to query the capabilities of the transport driver. |
| [IOCTL_BTHX_READ_HCI IOCTL](ni-bthxddi-ioctl_bthx_read_hci.md) | IOCTL_BTHX_READ_HCI is used to read Bluetooth ACL Data and Events from the transport layer. |
| [IOCTL_BTHX_SET_VERSION IOCTL](ni-bthxddi-ioctl_bthx_set_version.md) | IOCTL_BTHX_SET_VERSION is used to inform the transport driver of the version of the extensibility interface being used. |
| [IOCTL_BTHX_WRITE_HCI IOCTL](ni-bthxddi-ioctl_bthx_write_hci.md) | IOCTL_BTHX_WRITE_HCI is used to write Bluetooth ACL Data and Commands to the transport layer. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_BTHX_HCI_PACKET_TYPE enumeration](ne-bthxddi-_bthx_hci_packet_type.md) | The BTHX_HCI_PACKET_TYPE enumeration lists the different types of packets being sent from the Bluetooth stack to the transport driver. |
| [_BTHX_SCO_SUPPORT enumeration](ne-bthxddi-_bthx_sco_support.md) | The BTHX_SCO_SUPPORT enumeration lists the different types of SCO supported by the transport driver. |
