---
UID: NC:dispmprt.DXGKCB_WRITE_DEVICE_SPACE
title: DXGKCB_WRITE_DEVICE_SPACE (dispmprt.h)
description: The DxgkCbWriteDeviceSpace function writes to a device configuration space or the expansion ROM of a display adapter.
old-location: display\dxgkcbwritedevicespace.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["DXGKCB_WRITE_DEVICE_SPACE callback function"]
ms.keywords: DXGKCB_WRITE_DEVICE_SPACE, DXGKCB_WRITE_DEVICE_SPACE callback, DpFunctions_947b42ba-4121-4f21-b361-29a63278feb0.xml, DxgkCbWriteDeviceSpace, DxgkCbWriteDeviceSpace callback function [Display Devices], display.dxgkcbwritedevicespace, dispmprt/DxgkCbWriteDeviceSpace
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
 - DXGKCB_WRITE_DEVICE_SPACE
 - dispmprt/DXGKCB_WRITE_DEVICE_SPACE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dispmprt.h
api_name:
 - DxgkCbWriteDeviceSpace
---

# DXGKCB_WRITE_DEVICE_SPACE callback function


## -description

The <b>DxgkCbWriteDeviceSpace</b> function writes to a device configuration space or the expansion ROM of a display adapter.

## -parameters

### -param DeviceHandle 

[in]
A handle that represents a display adapter. The display miniport driver previously obtained this handle in the <b>DeviceHandle</b> member of the <a href="/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgkrnl_interface">DXGKRNL_INTERFACE</a> structure that was passed to <a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a>.

### -param DataType 

[in]
The type of write transaction to be performed. This parameter must be one of the following values, which are defined in <i>Dispmprt.h</i>:





#### DXGK_WHICHSPACE_BRIDGE

Write to the parent bus device's configuration space.



#### DXGK_WHICHSPACE_CONFIG

Write to the display adapter's configuration space.



#### DXGK_WHICHSPACE_MCH

Write to the configuration space of a memory controller hub that is a peer to the adapter's parent bus.



#### DXGK_WHICHSPACE_ROM

Write to the display adapter's expansion ROM.

### -param Buffer 

[in]
A pointer to a buffer that supplies the data to be written to the configuration space.

### -param Offset 

[in]
The offset, in bytes, into the configuration space, at which the write transaction begins.

### -param Length 

[in]
The number of bytes to be written.

### -param BytesWritten 

[out]
A pointer to a ULONG-typed variable that receives the number of bytes actually written.

## -returns

<b>DxgkCbWriteDeviceSpace</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_INVALID_PARAMETER|The DeviceHandle, DataType, or Buffer parameter is invalid.|
|STATUS_UNSUCCESSFUL|The function was unable to write the data.|

## -see-also

<a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkcb_read_device_space">DxgkCbReadDeviceSpace</a>
