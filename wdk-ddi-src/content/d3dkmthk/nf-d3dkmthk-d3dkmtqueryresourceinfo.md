---
UID: NF:d3dkmthk.D3DKMTQueryResourceInfo
title: D3DKMTQueryResourceInfo function
author: windows-driver-content
description: The D3DKMTQueryResourceInfo function retrieves information about a shared resource.
old-location: display\d3dkmtqueryresourceinfo.htm
old-project: display
ms.assetid: d195634e-d626-43c9-8212-f32b95c1f526
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: OpenGL_Functions_77dad2ba-a352-4b1a-b2be-53c41589bf90.xml, D3DKMTQueryResourceInfo function [Display Devices], D3DKMTQueryResourceInfo, d3dkmthk/D3DKMTQueryResourceInfo, display.d3dkmtqueryresourceinfo
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Gdi32.dll
-	API-MS-Win-dx-d3dkmt-l1-1-0.dll
-	API-MS-Win-dx-d3dkmt-l1-1-1.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
apiname:
-	D3DKMTQueryResourceInfo
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTQueryResourceInfo function


## -description


The <b>D3DKMTQueryResourceInfo</b> function retrieves information about a shared resource.


## -syntax


````
NTSTATUS APIENTRY D3DKMTQueryResourceInfo(
  _Inout_ D3DKMT_QUERYRESOURCEINFO *pData
);
````


## -parameters






#### - pData [in, out]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_queryresourceinfo.md">D3DKMT_QUERYRESOURCEINFO</a> structure that contains parameters for retrieving information about a shared resource.


## -returns



<b>D3DKMTQueryResourceInfo</b> returns one of the following values:

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
Information about a shared resource was successfully retrieved.

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
<dt><b>STATUS_INTEGER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
The size of all of the private driver data was too big to return to the OpenGL ICD.

</td>
</tr>
</table>
 

This function might also return other NTSTATUS values.




## -remarks



The OpenGL ICD typically calls <b>D3DKMTQueryResourceInfo</b> to obtain information about the resource and then uses this information to allocate the appropriate buffers for a call to <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtopenresource.md">D3DKMTOpenResource</a>.

For an example of how an OpenGL ICD can use <b>D3DKMTQueryResourceInfo</b> to retrieve information about a shared resource, see the code example in <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtopenresource.md">D3DKMTOpenResource</a>.




## -see-also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_queryresourceinfo.md">D3DKMT_QUERYRESOURCEINFO</a>



<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtopenresource.md">D3DKMTOpenResource</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTQueryResourceInfo function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

