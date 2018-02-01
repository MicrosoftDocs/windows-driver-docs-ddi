---
UID: NF:d3dkmthk.D3DKMTConfigureSharedResource
title: D3DKMTConfigureSharedResource function
author: windows-driver-content
description: The D3DKMTConfigureSharedResource function configures a shared resource.
old-location: display\d3dkmtconfiguresharedresource.htm
old-project: display
ms.assetid: 3664ef23-f7bc-4a94-8085-aa5a3d0ba550
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: OpenGL_Functions_f95f6a64-49a7-4a93-a544-6d4315f12212.xml, display.d3dkmtconfiguresharedresource, PFND3DKMT_CONFIGURESHAREDRESOURCE, D3DKMTConfigureSharedResource, D3DKMTConfigureSharedResource function [Display Devices], d3dkmthk/D3DKMTConfigureSharedResource
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: D3DKMTConfigureSharedResource is supported beginning with the Windows 7 operating system.
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
-	D3DKMTConfigureSharedResource
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTConfigureSharedResource function


## -description


The <b>D3DKMTConfigureSharedResource</b> function configures a shared resource. 


## -syntax


````
NTSTATUS D3DKMTConfigureSharedResource(
  _In_ const D3DKMT_CONFIGURESHAREDRESOURCE *pData
);
````


## -parameters




### -param D3DKMT_CONFIGURESHAREDRESOURCE

TBD



#### - pData [in]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_configuresharedresource.md">D3DKMT_CONFIGURESHAREDRESOURCE</a> structure that specifies parameters to configure the shared resource. 


## -returns


<b>D3DKMTConfigureSharedResource</b> returns one of the following values:
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
The shared resource was successfully configured. 

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

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtconfiguresharedresource.md">D3DKMTConfigureSharedResource</a> could not complete because of insufficient memory.

</td>
</tr>
</table> 

This function might also return other <b>NTSTATUS</b> values.



## -see-also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_configuresharedresource.md">D3DKMT_CONFIGURESHAREDRESOURCE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTConfigureSharedResource function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

