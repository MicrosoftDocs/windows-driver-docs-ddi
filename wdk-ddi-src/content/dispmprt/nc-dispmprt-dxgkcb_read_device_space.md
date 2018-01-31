---
UID: NC:dispmprt.DXGKCB_READ_DEVICE_SPACE
title: DXGKCB_READ_DEVICE_SPACE
author: windows-driver-content
description: The DxgkCbReadDeviceSpace function reads from a device configuration space or the expansion ROM of a display adapter.
old-location: display\dxgkcbreaddevicespace.htm
old-project: display
ms.assetid: 118ea0b9-6463-4050-9f33-192a3d42fdce
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgkcbreaddevicespace, DxgkCbReadDeviceSpace callback function [Display Devices], DxgkCbReadDeviceSpace, DXGKCB_READ_DEVICE_SPACE, DXGKCB_READ_DEVICE_SPACE, dispmprt/DxgkCbReadDeviceSpace, DpFunctions_54853b5b-487d-410e-a08d-eb777b3686e9.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	dispmprt.h
apiname:
-	DxgkCbReadDeviceSpace
product: Windows
targetos: Windows
req.typenames: SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
---

# DXGKCB_READ_DEVICE_SPACE callback


## -description


The <b>DxgkCbReadDeviceSpace</b> function reads from a device configuration space or the expansion ROM of a display adapter.


## -prototype


````
DXGKCB_READ_DEVICE_SPACE DxgkCbReadDeviceSpace;

NTSTATUS DxgkCbReadDeviceSpace(
  _In_  HANDLE DeviceHandle,
  _In_  ULONG  DataType,
  _In_  PVOID  Buffer,
  _In_  ULONG  Offset,
  _In_  ULONG  Length,
  _Out_ PULONG BytesRead
)
{ ... }
````


## -parameters




#### - DeviceHandle [in]

A handle that represents a display adapter. The display miniport driver previously obtained this handle in the <b>DeviceHandle</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560942">DXGKRNL_INTERFACE</a> structure that was passed to <a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a>.


#### - DataType [in]

The type of read transaction to be performed. This parameter must be one of the following values, which are defined in <i>Dispmprt.h</i>.




#### DXGK_WHICHSPACE_BRIDGE

Read from the PCI Express (PCIe) root port's configuration space.


#### DXGK_WHICHSPACE_CONFIG

Read from the display adapter's configuration space.


#### DXGK_WHICHSPACE_MCH

Read from the configuration space of a memory controller hub that is a peer to the adapter's parent bus.


#### DXGK_WHICHSPACE_ROM

Read from the display adapter's expansion ROM.


#### - Buffer [in]

A pointer to a caller-allocated buffer that receives the data read from the configuration space or ROM.


#### - Offset [in]

The offset, into the configuration space or the expansion ROM, at which the read transaction begins.


#### - Length [in]

The number of bytes to be read.


#### - BytesRead [out]

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

<a href="..\dispmprt\nc-dispmprt-dxgkcb_write_device_space.md">DxgkCbWriteDeviceSpace</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKCB_READ_DEVICE_SPACE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

