---
UID: NC:dispmprt.DXGKCB_READ_DEVICE_SPACE
title: DXGKCB_READ_DEVICE_SPACE
author: windows-driver-content
description: The DxgkCbReadDeviceSpace function reads from a device configuration space or the expansion ROM of a display adapter.
old-location: display\dxgkcbreaddevicespace.htm
old-project: display
ms.assetid: 118ea0b9-6463-4050-9f33-192a3d42fdce
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKCB_READ_DEVICE_SPACE, DpFunctions_54853b5b-487d-410e-a08d-eb777b3686e9.xml, DxgkCbReadDeviceSpace, DxgkCbReadDeviceSpace callback function [Display Devices], display.dxgkcbreaddevicespace, dispmprt/DxgkCbReadDeviceSpace
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	DxgkCbReadDeviceSpace
product: Windows
targetos: Windows
req.typenames: SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
---

# DXGKCB_READ_DEVICE_SPACE callback


## -description


The <b>DxgkCbReadDeviceSpace</b> function reads from a device configuration space or the expansion ROM of a display adapter.


## -parameters




### -param DeviceHandle [in]

A handle that represents a display adapter. The display miniport driver previously obtained this handle in the <b>DeviceHandle</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560942">DXGKRNL_INTERFACE</a> structure that was passed to <a href="https://msdn.microsoft.com/ffacbb39-2581-4207-841d-28ce57fbc64d">DxgkDdiStartDevice</a>.


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
  The function was unable to read the data.

</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/797d6b0c-91a4-4923-ad40-937cfde50067">DxgkCbWriteDeviceSpace</a>
 

 

