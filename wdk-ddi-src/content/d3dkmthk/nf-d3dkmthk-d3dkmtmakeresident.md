---
UID: NF:d3dkmthk.D3DKMTMakeResident
title: D3DKMTMakeResident function
author: windows-driver-content
description: D3DKMTMakeResident is used to add a resource to the device residency list and increment the residency reference count on this allocation.
old-location: display\d3dkmtmakeresident.htm
old-project: display
ms.assetid: 5F4E17CB-3B8B-4BBA-A819-B8E28183F1CB
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3dkmtmakeresident, d3dkmthk/D3DKMTMakeResident, D3DKMTMakeResident, D3DKMTMakeResident function [Display Devices]
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
-	D3DKMTMakeResident
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTMakeResident function


## -description


<b>D3DKMTMakeResident</b> is used to add a resource to the device residency list and increment the residency reference count on this allocation.


## -syntax


````
EXTERN_C _Check_return_ NTSTATUS APIENTRY D3DKMTMakeResident(
  _Inout_ D3DDDI_MAKERESIDENT *pData
);
````


## -parameters





#### - pData [in, out]

A pointer to a <a href="..\d3dukmdt\ns-d3dukmdt-d3dddi_makeresident.md">D3DDDI_MAKERESIDENT</a> structure that describes the operation.


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

<a href="..\d3dukmdt\ns-d3dukmdt-d3dddi_makeresident.md">D3DDDI_MAKERESIDENT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTMakeResident function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

