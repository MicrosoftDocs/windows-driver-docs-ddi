---
UID: NF:d3dkmthk.D3DKMTQueryAllocationResidency
title: D3DKMTQueryAllocationResidency function
author: windows-driver-content
description: The D3DKMTQueryAllocationResidency function retrieves the residency status of a resource or list of allocations.
old-location: display\d3dkmtqueryallocationresidency.htm
old-project: display
ms.assetid: f9522de0-54cd-4afd-b8cd-06f229ac1325
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMTQueryAllocationResidency, D3DKMTQueryAllocationResidency function [Display Devices], OpenGL_Functions_4efd6e87-91b6-4cf2-8691-0463a9ab218a.xml, d3dkmthk/D3DKMTQueryAllocationResidency, display.d3dkmtqueryallocationresidency
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
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
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Gdi32.dll
-	API-MS-Win-dx-d3dkmt-l1-1-0.dll
-	API-MS-Win-dx-d3dkmt-l1-1-1.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
-	D3DKMTQueryAllocationResidency
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTQueryAllocationResidency function


## -description


The <b>D3DKMTQueryAllocationResidency</b> function retrieves the residency status of a resource or list of allocations.


## -syntax


````
NTSTATUS APIENTRY D3DKMTQueryAllocationResidency(
  _In_ const D3DKMT_QUERYALLOCATIONRESIDENCY *pData
);
````


## -parameters




### -param D3DKMT_QUERYALLOCATIONRESIDENCY

TBD




#### - pData [in]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_queryallocationresidency.md">D3DKMT_QUERYALLOCATIONRESIDENCY</a> structure that contains information for retrieving the residency status of a resource or list of allocations.


## -returns



<b>D3DKMTQueryAllocationResidency</b> returns one of the following values:

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
Residency status for allocations was successfully retrieved.

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
</table>
 

This function might also return other NTSTATUS values.




## -see-also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_queryallocationresidency.md">D3DKMT_QUERYALLOCATIONRESIDENCY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTQueryAllocationResidency function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

