---
UID: NA:ntddpcm
ms.assetid: 4c1a57f9-d840-38ed-bb42-d0f3a4965439
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Ntddpcm.h header



This header is used by PCMCIA. For more information, see
- [PCMCIA](../_PCMCIA/index.md)

Ntddpcm.h contain these programming interfaces:


## Callback functions

| Title   | Description   |
| ---- |:---- |
| [PCMCIA_IS_WRITE_PROTECTED callback](nc-ntddpcm-pcmcia_is_write_protected.md) | The PCMCIA_IS_WRITE_PROTECTED interface routine returns the write-protect condition of a PCMCIA memory card. |
| [PCMCIA_MODIFY_MEMORY_WINDOW callback](nc-ntddpcm-pcmcia_modify_memory_window.md) | The PCMCIA_MODIFY_MEMORY_WINDOW interface routine sets the attributes of a memory window for a PCMCIA memory card. The memory window is mapped by the PCMCIA bus driver. |
| [PCMCIA_SET_VPP callback](nc-ntddpcm-pcmcia_set_vpp.md) | The PCMCIA_SET_VPP interface routine sets the power level of the Vpp PCMCIA pin (secondary power source). |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_PCMCIA_INTERFACE_STANDARD structure](ns-ntddpcm-_pcmcia_interface_standard.md) | The PCMCIA bus driver makes the PCMCIA_INTERFACE_STANDARD interface available to PCMCIA memory card drivers in order to allow them to make direct calls to the bus driver without allocating IRPs. |
| [_PCMCIA_SOCKET_INFORMATION structure](ns-ntddpcm-_pcmcia_socket_information.md) | The PCMCIA_SOCKET_INFORMATION structure is used in conjunction with the IOCTL_SOCKET_INFORMATION request to retrieve socket configuration and state data. |
| [_TUPLE_REQUEST structure](ns-ntddpcm-_tuple_request.md) | The TUPLE_REQUEST structure is used in conjunction with the IOCTL_GET_TUPLE_DATA request to retrieve tuple data from a PC Card's or CardBus card's attribute memory. |

## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_GET_TUPLE_DATA IOCTL](ni-ntddpcm-ioctl_get_tuple_data.md) | This request retrieves tuple data that is stored in a PC Card's or CardBus card's attribute memory. |
| [IOCTL_SOCKET_INFORMATION IOCTL](ni-ntddpcm-ioctl_socket_information.md) | This request retrieves socket information for the socket that is indicated by the caller. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_PCMCIA_CONTROLLER_CLASS enumeration](ne-ntddpcm-_pcmcia_controller_class.md) | The PCMCIA_CONTROLLER_CLASS enumeration lists the different sorts of PC Card and CardBus controllers. |
