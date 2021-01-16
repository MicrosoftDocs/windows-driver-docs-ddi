---
UID: NS:usbfnattach._USBFN_INTERFACE_ATTACH
title: _USBFN_INTERFACE_ATTACH (usbfnattach.h)
description: Stores pointers to driver-implemented callback functions for handling attach and detach operations.
old-location: buses\usbfn_interface_attach.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["USBFN_INTERFACE_ATTACH structure"]
ms.keywords: "*PUSBFN_INTERFACE_ATTACH, PUSBFN_INTERFACE_ATTACH, PUSBFN_INTERFACE_ATTACH structure pointer [Buses], USBFN_INTERFACE_ATTACH, USBFN_INTERFACE_ATTACH structure [Buses], _USBFN_INTERFACE_ATTACH, buses.usbfn_interface_attach, usbfnattach/PUSBFN_INTERFACE_ATTACH, usbfnattach/USBFN_INTERFACE_ATTACH"
req.header: usbfnattach.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: USBFN_INTERFACE_ATTACH, *PUSBFN_INTERFACE_ATTACH
f1_keywords:
 - _USBFN_INTERFACE_ATTACH
 - usbfnattach/_USBFN_INTERFACE_ATTACH
 - PUSBFN_INTERFACE_ATTACH
 - usbfnattach/PUSBFN_INTERFACE_ATTACH
 - USBFN_INTERFACE_ATTACH
 - usbfnattach/USBFN_INTERFACE_ATTACH
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - usbfnattach.h
api_name:
 - _USBFN_INTERFACE_ATTACH
 - PUSBFN_INTERFACE_ATTACH
 - USBFN_INTERFACE_ATTACH
---

# _USBFN_INTERFACE_ATTACH structure


## -description

Stores pointers to driver-implemented callback functions for handling attach and detach operations.

## -struct-fields

### -field InterfaceHeader

The interface version number.

### -field GetAttachAction

A pointer to the driver's implementation of the <a href="/windows-hardware/drivers/ddi/usbfnattach/nc-usbfnattach-usbfn_get_attach_action">USBFN_GET_ATTACH_ACTION</a> callback function.

### -field GetAttachActionAbortOperation

A pointer to the driver's implementation of the <a href="/windows-hardware/drivers/ddi/usbfnattach/nc-usbfnattach-usbfn_get_attach_action_abort">USBFN_GET_ATTACH_ACTION_ABORT</a> callback function.

### -field SetDeviceState

A pointer to the driver's implementation of the <a href="/windows-hardware/drivers/ddi/usbfnattach/nc-usbfnattach-usbfn_set_device_state">USBFN_SET_DEVICE_STATE</a> callback function.

## -see-also

<a href="/previous-versions/windows/hardware/drivers/mt188012(v=vs.85)">USB filter driver for supporting proprietary chargers</a>

