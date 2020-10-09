---
UID: NC:dispmprt.DXGKCB_IS_DEVICE_PRESENT
title: DXGKCB_IS_DEVICE_PRESENT (dispmprt.h)
description: The DxgkCbIsDevicePresent function determines whether a specified PCI device is present.
old-location: display\dxgkcbisdevicepresent.htm
tech.root: display
ms.assetid: 82716a1a-e361-40ad-b3cd-bdcd3abc75f8
ms.date: 05/10/2018
keywords: ["DXGKCB_IS_DEVICE_PRESENT callback function"]
ms.keywords: DXGKCB_IS_DEVICE_PRESENT, DXGKCB_IS_DEVICE_PRESENT callback, DpFunctions_0ef5f8dd-52b6-4bf6-a19b-f87043ff6d18.xml, DxgkCbIsDevicePresent, DxgkCbIsDevicePresent callback function [Display Devices], display.dxgkcbisdevicepresent, dispmprt/DxgkCbIsDevicePresent
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - DXGKCB_IS_DEVICE_PRESENT
 - dispmprt/DXGKCB_IS_DEVICE_PRESENT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dispmprt.h
api_name:
 - DxgkCbIsDevicePresent
---

# DXGKCB_IS_DEVICE_PRESENT callback function


## -description

The <b>DxgkCbIsDevicePresent</b> function determines whether a specified PCI device is present.

## -parameters

### -param DeviceHandle 

[in]
A handle that represents a display adapter. The display miniport driver previously obtained this handle in the <b>DeviceHandle</b> member of the <a href="/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgkrnl_interface">DXGKRNL_INTERFACE</a> structure that was passed to <a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a>.

### -param DevicePresenceParameters 

[in]
A pointer to a PCI_DEVICE_PRESENCE_PARAMETERS structure (defined in <i>Wdm.h</i>) that the caller fills in with information that identifies the device.

### -param DevicePresent 

[out]
A pointer to a Boolean variable that receives <b>TRUE</b> if the device is present or <b>FALSE</b> if the device is not present.

## -returns

<b>DxgkCbIsDevicePresent</b> returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.