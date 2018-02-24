---
UID: NF:d3dkmthk.D3DKMTOpenSynchronizationObject
title: D3DKMTOpenSynchronizationObject function
author: windows-driver-content
description: The D3DKMTOpenSynchronizationObject function opens a kernel-mode synchronization object.
old-location: display\d3dkmtopensynchronizationobject.htm
old-project: display
ms.assetid: e6316816-5260-4dd5-9c44-897ed5a88cc8
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: d3dkmthk/D3DKMTOpenSynchronizationObject, display.d3dkmtopensynchronizationobject, D3DKMTOpenSynchronizationObject function [Display Devices], D3DKMTOpenSynchronizationObject, OpenGL_Functions_c6ae5181-a478-47d7-8f0c-49f4f5a7f318.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: D3DKMTOpenSynchronizationObject is supported beginning with the Windows 7 operating system.
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
-	D3DKMTOpenSynchronizationObject
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTOpenSynchronizationObject function


## -description


The <b>D3DKMTOpenSynchronizationObject</b> function opens a kernel-mode synchronization object.


## -syntax


````
NTSTATUS D3DKMTOpenSynchronizationObject(
  _Inout_ D3DKMT_OPENSYNCHRONIZATIONOBJECT *pData
);
````


## -parameters






#### - pData [in, out]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_opensynchronizationobject.md">D3DKMT_OPENSYNCHRONIZATIONOBJECT</a> structure that describes a shared synchronization object to open. 


## -returns



<b>D3DKMTOpenSynchronizationObject</b> returns one of the following values:

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
The kernel-mode synchronization object was successfully opened. 

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

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtopensynchronizationobject.md">D3DKMTOpenSynchronizationObject</a> could not complete because of insufficient memory. 

</td>
</tr>
</table>
 

This function might also return other <b>NTSTATUS</b> values.




## -see-also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_opensynchronizationobject.md">D3DKMT_OPENSYNCHRONIZATIONOBJECT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTOpenSynchronizationObject function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

