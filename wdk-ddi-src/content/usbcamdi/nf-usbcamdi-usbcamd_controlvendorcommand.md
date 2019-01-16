---
UID: NF:usbcamdi.USBCAMD_ControlVendorCommand
title: USBCAMD_ControlVendorCommand function
description: The USBCAMD_ControlVendorCommand function sends vendor-specific commands to the control pipe.
old-location: stream\usbcamd_controlvendorcommand.htm
tech.root: stream
ms.assetid: 3bd11885-2c33-4d4d-b9e8-8eff79eb9c61
ms.date: 04/23/2018
ms.keywords: USBCAMD_ControlVendorCommand, USBCAMD_ControlVendorCommand function [Streaming Media Devices], stream.usbcamd_controlvendorcommand, usbcamdi/USBCAMD_ControlVendorCommand, usbcmdpr_71f3fad0-03ef-4328-90cf-d556de6736f5.xml
ms.topic: function
req.header: usbcamdi.h
req.include-header: Usbcamdi.h
req.target-type: Desktop
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
req.lib: Usbcamd2.lib
req.dll: 
req.irql: ">= PASSIVE_LEVEL (See Remarks section)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	usbcamd2.lib
-	usbcamd2.dll
api_name:
-	USBCAMD_ControlVendorCommand
product:
- Windows
targetos: Windows
req.typenames: 
---

# USBCAMD_ControlVendorCommand function


## -description


The <b>USBCAMD_ControlVendorCommand</b> function sends vendor-specific commands to the control pipe.


## -parameters




### -param DeviceContext [in]

Pointer to device-specific context.


### -param Request [in]

Specifies the value of the <b>Request</b> field for the vendor command.


### -param Value [in]

Specifies the value of the <b>Value</b> field for the vendor command.


### -param Index [in]

Specifies the value of the <b>Index</b> field for the vendor command.


### -param Buffer [in, out, optional]

Pointer to a data buffer if the command has data. If the command does not have any data, this value is <b>NULL</b>.


### -param BufferLength [in, out]

Pointer to the buffer length value. Buffer length is expressed in bytes. If the value of <i>Buffer</i> is <b>NULL</b>, <i>BufferLength</i> may also be <b>NULL</b>.


### -param GetData [in]

<i>GetData</i> indicates data was sent from the device to the host.


### -param CommandComplete [in, optional]

Pointer to a camera minidriver defined <a href="https://msdn.microsoft.com/library/windows/hardware/ff557713">CommandCompleteFunction</a>, which is called when the bulk read or write is completed. This value can be <b>NULL</b>.


### -param CommandContext [in, optional]

Pointer to a block of memory, that is passed as an argument to the camera minidriver defined <a href="https://msdn.microsoft.com/library/windows/hardware/ff557713">CommandCompleteFunction</a>.


## -returns



<b>USBCAMD_ControlVendorCommand </b>returns the NTSTATUS code from vendor command. Other possible error codes include:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The vendor command is deferred.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There are insufficient resources to allocate the vendor command.

</td>
</tr>
</table>
 




## -remarks



This function may be called at IRQL &gt;= PASSIVE_LEVEL. If the function is called at IRQL &gt; PASSIVE_LEVEL, the command is deferred. After completion, the camera minidriver defined <a href="https://msdn.microsoft.com/library/windows/hardware/ff557713">CommandCompleteFunction</a> is called and passed the value in the <i>CommandContext</i> argument<i>.</i>




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557713">CommandCompleteFunction</a>
 

 

