---
UID: NF:d3dkmthk.D3DKMTCreateContextVirtual
title: D3DKMTCreateContextVirtual function
author: windows-driver-content
description: The D3DKMTCreateContextVirtual function creates a kernel mode device context that supports virtual addressing.
old-location: display\d3dkmtcreatecontextvirtual.htm
old-project: display
ms.assetid: 1E95228E-7513-46D2-8402-28CA6D26F3EB
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3dkmtcreatecontextvirtual, d3dkmthk/D3DKMTCreateContextVirtual, D3DKMTCreateContextVirtual, D3DKMTCreateContextVirtual function [Display Devices]
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	DllExport
apilocation: 
-	GDI32.dll
-	API-MS-Win-DX-D3DKMT-L1-1-1.dll
-	GDI32.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
apiname: 
-	D3DKMTCreateContextVirtual
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTCreateContextVirtual function


## -description


The <b>D3DKMTCreateContextVirtual</b> function creates a kernel mode device context that supports virtual addressing.


## -syntax


````
NTSTATUS APIENTRY D3DKMTCreateContextVirtual(
  _In_ D3DKMT_CREATECONTEXTVIRTUAL *pData
);
````


## -parameters





#### - pData [in]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_createcontextvirtual.md">D3DKMT_CREATECONTEXTVIRTUAL</a> structure that describes the kernel-mode device context.


## -returns


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
The device context was successfully created.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DEVICE_REMOVED</b></dt>
</dl>
</td>
<td width="60%">
The graphics adapter was stopped or the display device was reset.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Parameters were validated and determined to be incorrect.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">
<b>D3DKMTCreateContextVirtual</b> could not complete because of insufficient memory.

</td>
</tr>
</table> 

This function might also return other <b>NTSTATUS</b> values.



## -see-also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_createcontextvirtual.md">D3DKMT_CREATECONTEXTVIRTUAL</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTCreateContextVirtual function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

