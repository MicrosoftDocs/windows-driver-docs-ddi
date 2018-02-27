---
UID: NA:avc
ms.assetid: 4dc7acf6-1c5d-3be6-ba74-d76d6b3b9318
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Avc.h header



This header is used by Streaming media devices. For more information, see
- [Streaming media devices](../_stream/index.md)

Avc.h contain these programming interfaces:


## Callback functions

| Title   | Description   |
| ---- |:---- |
| [PFNAVCINTERSECTHANDLER callback](nc-avc-pfnavcintersecthandler.md) | The AV/C intersect handler determines if the data ranges are compatible. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_AVCCONNECTINFO structure](ns-avc-_avcconnectinfo.md) | The AVCCONNECTINFO structure is used to initialize a subunit driver and establish pin connections. |
| [_AVCPRECONNECTINFO structure](ns-avc-_avcpreconnectinfo.md) | The AVCPRECONNECTINFO structure is used to initialize a subunit driver and establish pin connections. |
| [_AVC_COMMAND_IRB structure](ns-avc-_avc_command_irb.md) | The AVC_COMMAND_IRB structure defines a structure that contains an AV/C command and response pair. |
| [_AVC_EXT_PLUG_COUNTS structure](ns-avc-_avc_ext_plug_counts.md) | The AVC_EXT_PLUG_COUNTS structure describes the number of external plugs on the subunit. |
| [_AVC_IRB structure](ns-avc-_avc_irb.md) | The AVC_IRB structure is an I/O Request Block (IRB) header structure where a function number is stored. |
| [_AVC_MULTIFUNC_IRB structure](ns-avc-_avc_multifunc_irb.md) | The AVC_MULTIFUNC_IRB structure contains other AV/C related structures in a union. |
| [_AVC_PEER_DO_LIST structure](ns-avc-_avc_peer_do_list.md) | The AVC_PEER_DO_LIST describes all nonvirtual (peer) instances of avc.sys. |
| [_AVC_PEER_DO_LOCATOR structure](ns-avc-_avc_peer_do_locator.md) | The AVC_PEER_DO_LOCATOR describes nonvirtual (peer) instances of avc.sys. |
| [_AVC_PIN_COUNT structure](ns-avc-_avc_pin_count.md) | The AVC_PIN_COUNT structure specifies the number of pins on an AV/C subunit device. |
| [_AVC_PIN_DESCRIPTOR structure](ns-avc-_avc_pin_descriptor.md) | The AVC_PIN_DESCRIPTOR structure describes a pin on an AV/C subunit device. |
| [_AVC_PIN_ID structure](ns-avc-_avc_pin_id.md) | The AVC_PIN_ID structure describes a pin on a subunit. |
| [_AVC_PRECONNECT_INFO structure](ns-avc-_avc_preconnect_info.md) | The AVC_PRECONNECT_INFO structure specifies the preconnection information for the specified pin ID (zero-based offset) on an AV/C subunit device. |
| [_AVC_SETCONNECT_INFO structure](ns-avc-_avc_setconnect_info.md) | The AVC_SETCONNECT_INFO structure is used to initialize a subunit driver and establish pin connections. |
| [_AVC_SUBUNIT_ADDR_SPEC structure](ns-avc-_avc_subunit_addr_spec.md) | The AVC_SUBUNIT_ADDR_SPEC structure is used with virtual instances of avc.sys to describe virtual subunit addresses. |
| [_AVC_SUBUNIT_INFO_BLOCK structure](ns-avc-_avc_subunit_info_block.md) | The AVC_SUBUNIT_INFO_BLOCK structure describes subunit information. |
| [_AVC_UNIQUE_ID structure](ns-avc-_avc_unique_id.md) | The AVC_UNIQUE_ID describe the unique ID of the AV/C unit. |

## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_AVC_BUS_RESET IOCTL](ni-avc-ioctl_avc_bus_reset.md) | The IOCTL_AVC_BUS_RESET I/O control code allows the caller to complete any previous IOCTL_AVC_UPDATE_VIRTUAL_SUBUNIT_INFO and IOCTL_AVC_REMOVE_VIRTUAL_SUBUNIT_INFO control requests that did not use the AVC_SUBUNIT_ADDR_TRIGGERBUSRESET flag. |
| [IOCTL_AVC_CLASS IOCTL](ni-avc-ioctl_avc_class.md) | The IOCTL_AVC_CLASS I/O control code is supported only from kernel mode, using the IRP_MJ_INTERNAL_DEVICE_CONTROL dispatch.Avc.sys supports two device interfaces, depending upon the type of instance (peer or virtual). |
| [IOCTL_AVC_REMOVE_VIRTUAL_SUBUNIT_INFO IOCTL](ni-avc-ioctl_avc_remove_virtual_subunit_info.md) | The IOCTL_AVC_REMOVE_VIRTUAL_SUBUNIT_INFO I/O control code controls the enumeration of virtual subunits. |
| [IOCTL_AVC_UPDATE_VIRTUAL_SUBUNIT_INFO IOCTL](ni-avc-ioctl_avc_update_virtual_subunit_info.md) | The IOCTL_AVC_UPDATE_VIRTUAL_SUBUNIT_INFO I/O control code controls the enumeration of virtual subunits. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_KSPIN_FLAG_AVC enumeration](ne-avc-_kspin_flag_avc.md) | The KSPIN_FLAG_AVC enumeration type is used for connection management and in the AVC_FUNCTION_GET_CONNECTINFO function code. |
| [_tagAVC_FUNCTION enumeration](ne-avc-_tagavc_function.md) | The AVC_FUNCTION enumeration type is used to specify AV/C subunit functions. |
| [_tagAvcCommandType enumeration](ne-avc-_tagavccommandtype.md) | The AvcCommandType enumeration type is used to indicate the type of command issued by a subunit driver to its AV/C subunit through AVC_FUNCTION_COMMAND or AVC_FUNCTION_GET_REQUEST function codes. |
| [_tagAvcResponseCode enumeration](ne-avc-_tagavcresponsecode.md) | The AvcResponseCode enumeration type is used to indicate the type of response received by a subunit driver from its AV/C subunit through AVC_FUNCTION_COMMAND or AVC_FUNCTION_SEND_RESPONSE function codes. |
| [_tagAvcSubunitType enumeration](ne-avc-_tagavcsubunittype.md) | The AvcSubunitType enumeration type is used to indicate the type of AV/C subunit. |
