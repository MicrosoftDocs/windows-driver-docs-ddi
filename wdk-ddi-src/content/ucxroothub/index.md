---
UID: NA:ucxroothub
ms.assetid: f414bbf8-87c3-3f54-a115-be4e34efc66d
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Ucxroothub.h header



This header is used by Universal Serial Bus(USB). For more information, see
- [Universal Serial Bus(USB)](../_usbref/index.md)

Ucxroothub.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [UcxRootHubPortChanged function](nf-ucxroothub-ucxroothubportchanged.md) | Notifies UCX about a new port change event on the host controller. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [EVT_UCX_ROOTHUB_CONTROL_URB callback](nc-ucxroothub-evt_ucx_roothub_control_urb.md) | The client driver uses this callback type to implement handlers that UCX calls when it receives feature control requests on the USB hub. |
| [EVT_UCX_ROOTHUB_GET_20PORT_INFO callback](nc-ucxroothub-evt_ucx_roothub_get_20port_info.md) | The client driver's implementation that UCX calls when it receives a request for information about USB 2.0 ports on the root hub. |
| [EVT_UCX_ROOTHUB_GET_30PORT_INFO callback](nc-ucxroothub-evt_ucx_roothub_get_30port_info.md) | The client driver's implementation that UCX calls when it receives a request for information about USB 3.0 ports on the root hub. |
| [EVT_UCX_ROOTHUB_GET_INFO callback](nc-ucxroothub-evt_ucx_roothub_get_info.md) | The client driver's implementation that UCX calls when it receives a request for information about the root hub. |
| [EVT_UCX_ROOTHUB_INTERRUPT_TX callback](nc-ucxroothub-evt_ucx_roothub_interrupt_tx.md) | The client driver's implementation that UCX calls when it receives a request for information about changed ports. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_CONTROLLER_USB_20_HARDWARE_LPM_FLAGS structure](ns-ucxroothub-_controller_usb_20_hardware_lpm_flags.md) | Describes supported protocol capabilities for Link Power Management (LPM) in as defined the USB 2.0 specification. |
| [_HUB_INFO_FROM_PARENT structure](ns-ucxroothub-_hub_info_from_parent.md) | Describes information about a hub from its parent device. |
| [_PARENT_HUB_FLAGS structure](ns-ucxroothub-_parent_hub_flags.md) | This structure is used by the HUB_INFO_FROM_PARENT structure to get hub information from the parent. |
| [_ROOTHUB_20PORTS_INFO structure](ns-ucxroothub-_roothub_20ports_info.md) | This structure that has an array of 2.0 ports supported by the root hub. This structure is provided by UCX in a framework request in the EVT_UCX_ROOTHUB_GET_20PORT_INFO callback function. |
| [_ROOTHUB_20PORT_INFO structure](ns-ucxroothub-_roothub_20port_info.md) | Provides information about a USB 2.0 root hub port. This structure is passed by UCX in the EVT_UCX_ROOTHUB_GET_20PORT_INFO callback function. |
| [_ROOTHUB_30PORTS_INFO structure](ns-ucxroothub-_roothub_30ports_info.md) | Provides information about USB 3.0 root hub ports. This structure is passed by UCX in the EVT_UCX_ROOTHUB_GET_30PORT_INFO callback function. |
| [_ROOTHUB_30PORT_INFO structure](ns-ucxroothub-_roothub_30port_info.md) | Provides information about a USB 3.0 root hub port. This structure is passed by UCX in the EVT_UCX_ROOTHUB_GET_30PORT_INFO callback function. |
| [_ROOTHUB_30PORT_INFO_EX structure](ns-ucxroothub-_roothub_30port_info_ex.md) | Provides extended USB 3.0 port information about speed. |
| [_ROOTHUB_INFO structure](ns-ucxroothub-_roothub_info.md) | Provides information about a USB root hub. This structure is passed by UCX in the EVT_UCX_ROOTHUB_GET_INFO callback function. |
| [_UCX_ROOTHUB_CONFIG structure](ns-ucxroothub-_ucx_roothub_config.md) | Contains pointers to event callback functions for creating the root hub by calling UcxRootHubCreate. Initialize this structure by calling UCX_ROOTHUB_CONFIG_INIT initialization function (see Ucxclass.h). |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_CONTROLLER_TYPE enumeration](ne-ucxroothub-_controller_type.md) | This enumeration specifies if the USB host controller is an eXtensible Host Controller Interface (xHCI) controller. |
| [_TRISTATE enumeration](ne-ucxroothub-_tristate.md) | The TRISTATE enumeration indicates generic state values for true or false. |
