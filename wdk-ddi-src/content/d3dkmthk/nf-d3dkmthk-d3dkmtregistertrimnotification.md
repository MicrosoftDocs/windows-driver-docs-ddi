---
UID: NF:d3dkmthk.D3DKMTRegisterTrimNotification
title: D3DKMTRegisterTrimNotification function
author: windows-driver-content
description: D3DKMTRegisterTrimNotification is used by a kernel mode video memory manager to register and implement a callback for each kernel mode device to receive notifications from a graphics framework (such as OpenGL).
old-location: display\d3dkmtregistertrimnotification.htm
old-project: display
ms.assetid: 4D35ED8F-2D1E-4C0B-8302-CE651D47AF10
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMTRegisterTrimNotification, D3DKMTRegisterTrimNotification function [Display Devices], d3dkmthk/D3DKMTRegisterTrimNotification, display.d3dkmtregistertrimnotification
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: GDI32.lib
req.dll: GDI32.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	GDI32.dll
-	API-MS-Win-DX-D3DKMT-L1-1-1.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
-	D3DKMTRegisterTrimNotification
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTRegisterTrimNotification function


## -description


<b>D3DKMTRegisterTrimNotification</b> is used by a kernel mode video memory manager to register and implement a callback for each kernel mode device to receive notifications from a graphics framework (such as OpenGL).
<div class="alert"><b>Note</b>  The callback must be unregistered prior to unloading the module that contains the callback function and destroying the registered kernel mode device.</div><div> </div>

## -parameters




### -param Arg1

TBD




#### - pData [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn906802">D3DKMT_REGISTERTRIMNOTIFICATION</a> structure that describes the operation.


## -returns



Returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The operation was performed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER </b></dt>
</dl>
</td>
<td width="60%">

         Parameters were validated and determined to be incorrect.

</td>
</tr>
</table>
 

This function might also return other <b>NTSTATUS</b> values.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn906787">D3DKMTUnregisterTrimNotification</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn906802">D3DKMT_REGISTERTRIMNOTIFICATION</a>
 

 

