---
UID: NC:dispmprt.DXGKCB_WRITE_DEVICE_SPACE
title: DXGKCB_WRITE_DEVICE_SPACE
author: windows-driver-content
description: The DxgkCbWriteDeviceSpace function writes to a device configuration space or the expansion ROM of a display adapter.
old-location: display\dxgkcbwritedevicespace.htm
tech.root: display
ms.assetid: 797d6b0c-91a4-4923-ad40-937cfde50067
ms.date: 05/10/2018
ms.keywords: DXGKCB_WRITE_DEVICE_SPACE, DXGKCB_WRITE_DEVICE_SPACE callback, DpFunctions_947b42ba-4121-4f21-b361-29a63278feb0.xml, DxgkCbWriteDeviceSpace, DxgkCbWriteDeviceSpace callback function [Display Devices], display.dxgkcbwritedevicespace, dispmprt/DxgkCbWriteDeviceSpace
ms.topic: callback
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	dispmprt.h
api_name:
-	DxgkCbWriteDeviceSpace
product:
- Windows
targetos: Windows
req.typenames: 
---

# DXGKCB_WRITE_DEVICE_SPACE callback function


## -description


The <b>DxgkCbWriteDeviceSpace</b> function writes to a device configuration space or the expansion ROM of a display adapter.


## -parameters




### -param DeviceHandle [in]

A handle that represents a display adapter. The display miniport driver previously obtained this handle in the <b>DeviceHandle</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560942">DXGKRNL_INTERFACE</a> structure that was passed to <a href="https://msdn.microsoft.com/ffacbb39-2581-4207-841d-28ce57fbc64d">DxgkDdiStartDevice</a>.


### -param DataType [in]

The type of write transaction to be performed. This parameter must be one of the following values, which are defined in <i>Dispmprt.h</i>:





#### DXGK_WHICHSPACE_BRIDGE

Write to the parent bus device's configuration space.



#### DXGK_WHICHSPACE_CONFIG

Write to the display adapter's configuration space.



#### DXGK_WHICHSPACE_MCH

Write to the configuration space of a memory controller hub that is a peer to the adapter's parent bus.



#### DXGK_WHICHSPACE_ROM

Write to the display adapter's expansion ROM.


### -param Buffer [in]

A pointer to a buffer that supplies the data to be written to the configuration space.


### -param Offset [in]

The offset, in bytes, into the configuration space, at which the write transaction begins.


### -param Length [in]

The number of bytes to be written.


### -param BytesWritten [out]

A pointer to a ULONG-typed variable that receives the number of bytes actually written.


## -returns



<b>DxgkCbWriteDeviceSpace</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>  STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
  The function succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>  STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
  The <i>DeviceHandle</i>, <i>DataType</i>, or <i>Buffer</i> parameter is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>  STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
  The function was unable to write the data.

</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/118ea0b9-6463-4050-9f33-192a3d42fdce">DxgkCbReadDeviceSpace</a>
 

 

