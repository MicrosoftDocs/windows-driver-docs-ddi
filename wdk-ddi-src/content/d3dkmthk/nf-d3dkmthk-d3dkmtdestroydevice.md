---
UID: NF:d3dkmthk.D3DKMTDestroyDevice
title: D3DKMTDestroyDevice function
author: windows-driver-content
description: The D3DKMTDestroyDevice function releases a kernel-mode device context.
old-location: display\d3dkmtdestroydevice.htm
old-project: display
ms.assetid: 7699214a-0cd2-401a-9f66-199d181abce4
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMTDestroyDevice, display.d3dkmtdestroydevice, OpenGL_Functions_66b283a1-deee-4a49-a02d-217567d35873.xml, d3dkmthk/D3DKMTDestroyDevice, D3DKMTDestroyDevice function [Display Devices]
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
-	D3DKMTDestroyDevice
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTDestroyDevice function


## -description


The <b>D3DKMTDestroyDevice</b> function releases a kernel-mode device context.


## -syntax


````
NTSTATUS D3DKMTDestroyDevice(
  _In_ const D3DKMT_DESTROYDEVICE *pData
);
````


## -parameters




### -param D3DKMT_DESTROYDEVICE

TBD



#### - pData [in]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_destroydevice.md">D3DKMT_DESTROYDEVICE</a> structure that contains the handle to the kernel-mode device context.


## -returns


<b>D3DKMTDestroyDevice</b> returns one of the following values:
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
The device context was successfully released.

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

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_destroydevice.md">D3DKMT_DESTROYDEVICE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTDestroyDevice function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

