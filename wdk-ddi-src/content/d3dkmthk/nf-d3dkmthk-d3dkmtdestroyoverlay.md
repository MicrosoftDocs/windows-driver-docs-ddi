---
UID: NF:d3dkmthk.D3DKMTDestroyOverlay
title: D3DKMTDestroyOverlay function
author: windows-driver-content
description: The D3DKMTDestroyOverlay function destroys a kernel-mode overlay object.
old-location: display\d3dkmtdestroyoverlay.htm
old-project: display
ms.assetid: 8a5eef07-97b7-43ca-b8e0-15af89aa7d82
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.d3dkmtdestroyoverlay, d3dkmthk/D3DKMTDestroyOverlay, OpenGL_Functions_57efc2f4-dbbe-4f91-b724-036b5231c058.xml, D3DKMTDestroyOverlay function [Display Devices], D3DKMTDestroyOverlay
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
-	D3DKMTDestroyOverlay
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTDestroyOverlay function


## -description


The <b>D3DKMTDestroyOverlay</b> function destroys a kernel-mode overlay object.


## -syntax


````
NTSTATUS D3DKMTDestroyOverlay(
  _In_ const D3DKMT_DESTROYOVERLAY *pData
);
````


## -parameters




### -param D3DKMT_DESTROYOVERLAY

TBD




#### - pData [in]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_destroyoverlay.md">D3DKMT_DESTROYOVERLAY</a> structure that contains the handle to the overlay to destroy.


## -returns



<b>D3DKMTDestroyOverlay</b> returns one of the following values:

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
The kernel-mode overlay object was successfully destroyed.

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




## -see-also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_destroyoverlay.md">D3DKMT_DESTROYOVERLAY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTDestroyOverlay function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

