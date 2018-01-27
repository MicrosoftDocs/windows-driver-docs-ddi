---
UID: NF:d3dkmthk.D3DKMTFreeGpuVirtualAddress
title: D3DKMTFreeGpuVirtualAddress function
author: windows-driver-content
description: D3DKMTFreeGpuVirtualAddress releases a range of graphics processing unit (GPU) virtual addresses, which was previously reserved or mapped.
old-location: display\d3dkmtfreegpuvirtualaddress.htm
old-project: display
ms.assetid: E076E9E6-FA7E-4F46-88B4-D3971E62DE1A
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dkmthk/D3DKMTFreeGpuVirtualAddress, display.d3dkmtfreegpuvirtualaddress, D3DKMTFreeGpuVirtualAddress, D3DKMTFreeGpuVirtualAddress function [Display Devices]
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
-	D3DKMTFreeGpuVirtualAddress
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTFreeGpuVirtualAddress function


## -description


<b>D3DKMTFreeGpuVirtualAddress</b> releases a range of graphics processing unit (GPU) virtual addresses, which was previously reserved or mapped. 


## -syntax


````
NTSTATUS APIENTRY D3DKMTFreeGpuVirtualAddress(
  _In_ const D3DKMT_FREEGPUVIRTUALADDRESS *pData
);
````


## -parameters




### -param D3DKMT_FREEGPUVIRTUALADDRESS

TBD



#### - pData [in]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_freegpuvirtualaddress.md">D3DKMT_FREEGPUVIRTUALADDRESS</a> structure that describes the operation.


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
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Parameters were validated and determined to be incorrect.

</td>
</tr>
</table> 

This function might also return other <b>NTSTATUS</b> values.



## -remarks


The freed virtual address should not be accessed immediately after the call. If there are outstanding <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtmapgpuvirtualaddress.md">MapGpuVirtualAddress</a> and <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtupdategpuvirtualaddress.md">UpdateGpuVirtualAddress</a> operations, which reference the virtual address, they will be ignored after the virtual address is freed. A new virtual address range can be allocated in place of the freed one immediately after return from the function.



## -see-also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_freegpuvirtualaddress.md">D3DKMT_FREEGPUVIRTUALADDRESS</a>

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtmapgpuvirtualaddress.md">MapGpuVirtualAddress</a>

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtupdategpuvirtualaddress.md">UpdateGpuVirtualAddress</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTFreeGpuVirtualAddress function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

