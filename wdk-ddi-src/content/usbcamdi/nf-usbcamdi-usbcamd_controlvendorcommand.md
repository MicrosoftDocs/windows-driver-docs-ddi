---
UID: NF:usbcamdi.USBCAMD_ControlVendorCommand
title: USBCAMD_ControlVendorCommand function
author: windows-driver-content
description: The USBCAMD_ControlVendorCommand function sends vendor-specific commands to the control pipe.
old-location: stream\usbcamd_controlvendorcommand.htm
old-project: stream
ms.assetid: 3bd11885-2c33-4d4d-b9e8-8eff79eb9c61
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , A, B, C, D, M, S, U, USBCAMD_ControlVendorCommand, USBCAMD_ControlVendorCommand function [Streaming Media Devices], V, _, a, d, e, l, m, n, o, r, stream.usbcamd_controlvendorcommand, t, usbcamdi/USBCAMD_ControlVendorCommand, usbcmdpr_71f3fad0-03ef-4328-90cf-d556de6736f5.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	usbcamd2.lib
-	usbcamd2.dll
apiname:
-	USBCAMD_ControlVendorCommand
product: Windows
targetos: Windows
req.typenames: USB_BUS_INTERFACE_USBDI_V3, *PUSB_BUS_INTERFACE_USBDI_V3
req.product: Windows 10 or later.
---

# USBCAMD_ControlVendorCommand function


## -description


The <b>USBCAMD_ControlVendorCommand</b> function sends vendor-specific commands to the control pipe.


## -syntax


````
NTSTATUS USBCAMD_ControlVendorCommand(
  _In_        PVOID                      DeviceContext,
  _In_        UCHAR                      Request,
  _In_        USHORT                     Value,
  _In_        USHORT                     Index,
  _Inout_opt_ PVOID                      Buffer,
  _Inout_     PULONG                     BufferLength,
  _In_        BOOLEAN                    GetData,
  _In_opt_    PCOMMAND_COMPLETE_FUNCTION CommandComplete,
  _In_opt_    PVOID                      CommandContext
);
````


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

Pointer to a camera minidriver defined <a href="..\usbcamdi\nc-usbcamdi-pcommand_complete_function.md">CommandCompleteFunction</a>, which is called when the bulk read or write is completed. This value can be <b>NULL</b>.


### -param CommandContext [in, optional]

Pointer to a block of memory, that is passed as an argument to the camera minidriver defined <a href="..\usbcamdi\nc-usbcamdi-pcommand_complete_function.md">CommandCompleteFunction</a>.


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



This function may be called at IRQL &gt;= PASSIVE_LEVEL. If the function is called at IRQL &gt; PASSIVE_LEVEL, the command is deferred. After completion, the camera minidriver defined <a href="..\usbcamdi\nc-usbcamdi-pcommand_complete_function.md">CommandCompleteFunction</a> is called and passed the value in the <i>CommandContext</i> argument<i>.</i>




## -see-also

<a href="..\usbcamdi\nc-usbcamdi-pcommand_complete_function.md">CommandCompleteFunction</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20USBCAMD_ControlVendorCommand function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

