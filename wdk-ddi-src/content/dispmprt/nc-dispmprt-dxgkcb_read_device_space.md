---
UID: NC:dispmprt.DXGKCB_READ_DEVICE_SPACE
title: DXGKCB_READ_DEVICE_SPACE (dispmprt.h)
description: The DxgkCbReadDeviceSpace function reads from a device configuration space or the expansion ROM of a display adapter.
old-location: display\dxgkcbreaddevicespace.htm
tech.root: display
ms.assetid: 118ea0b9-6463-4050-9f33-192a3d42fdce
ms.date: 05/10/2018
ms.keywords: DXGKCB_READ_DEVICE_SPACE, DXGKCB_READ_DEVICE_SPACE callback, DpFunctions_54853b5b-487d-410e-a08d-eb777b3686e9.xml, DxgkCbReadDeviceSpace, DxgkCbReadDeviceSpace callback function [Display Devices], display.dxgkcbreaddevicespace, dispmprt/DxgkCbReadDeviceSpace
f1_keywords:
 - "dispmprt/DxgkCbReadDeviceSpace"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- dispmprt.h
api_name:
- DxgkCbReadDeviceSpace
product:
- Windows
targetos: Windows
req.typenames: 
---

# DXGKCB_READ_DEVICE_SPACE callback function


## -description


The <b>DxgkCbReadDeviceSpace</b> function reads from a device configuration space or the expansion ROM of a display adapter.


## -parameters




### -param DeviceHandle [in]

A handle that represents a display adapter. The display miniport driver previously obtained this handle in the <b>DeviceHandle</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgkrnl_interface">DXGKRNL_INTERFACE</a> structure that was passed to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a>.


### -param DataType [in]

The type of read transaction to be performed. This parameter must be one of the following values, which are defined in <i>Dispmprt.h</i>.





#### DXGK_WHICHSPACE_BRIDGE

Read from the PCI Express (PCIe) root port's configuration space.



#### DXGK_WHICHSPACE_CONFIG

Read from the display adapter's configuration space.



#### DXGK_WHICHSPACE_MCH

Read from the configuration space of a memory controller hub that is a peer to the adapter's parent bus.



#### DXGK_WHICHSPACE_ROM

Read from the display adapter's expansion ROM.


### -param Buffer [in]

A pointer to a caller-allocated buffer that receives the data read from the configuration space or ROM.


### -param Offset [in]

The offset, into the configuration space or the expansion ROM, at which the read transaction begins.


### -param Length [in]

The number of bytes to be read.


### -param BytesRead [out]

A pointer to a ULONG-typed variable that receives the number of bytes actually read.


## -returns



<b>DxgkCbReadDeviceSpace</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_INVALID_PARAMETER|The DeviceHandle, DataType, or Buffer parameter is invalid.|
|STATUS_UNSUCCESSFUL|The function was unable to read the data.|



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkcb_write_device_space">DxgkCbWriteDeviceSpace</a>
 

 

