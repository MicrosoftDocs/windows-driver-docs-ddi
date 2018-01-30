---
UID: NF:d3dkmthk.D3DKMTOpenAdapterFromDeviceName
title: D3DKMTOpenAdapterFromDeviceName function
author: windows-driver-content
description: The D3DKMTOpenAdapterFromDeviceName function maps a device name to a graphics adapter handle and, if the adapter contains multiple monitor outputs, to one of those outputs.
old-location: display\d3dkmtopenadapterfromdevicename.htm
old-project: display
ms.assetid: bff9d991-63a1-47af-a351-073c82c0d31c
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMTOpenAdapterFromDeviceName function [Display Devices], display.d3dkmtopenadapterfromdevicename, D3DKMTOpenAdapterFromDeviceName, OpenGL_Functions_8298711e-9466-4e00-b77a-0c7a1ee88bed.xml, d3dkmthk/D3DKMTOpenAdapterFromDeviceName
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
-	D3DKMTOpenAdapterFromDeviceName
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTOpenAdapterFromDeviceName function


## -description


The <b>D3DKMTOpenAdapterFromDeviceName</b> function maps a device name to a graphics adapter handle and, if the adapter contains multiple monitor outputs, to one of those outputs.


## -syntax


````
NTSTATUS D3DKMTOpenAdapterFromDeviceName(
  _Inout_ D3DKMT_OPENADAPTERFROMDEVICENAME *pData
);
````


## -parameters





#### - pData [in, out]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_openadapterfromdevicename.md">D3DKMT_OPENADAPTERFROMDEVICENAME</a> structure that describes the parameters that are required to perform the mapping.


## -returns


<b>D3DKMTOpenAdapterFromDeviceName</b> returns one of the following values:
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
The mapping was performed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Parameters were validated and determined to be incorrect or the Windows Vista display driver model was not used.

</td>
</tr>
</table> 

This function might also return other NTSTATUS values.



## -remarks


A graphics adapter corresponds to a video card. A monitor output corresponds to a head on a video card. A system with a single video card contains only one adapter. However, if the video card supports multiple heads, it supports outputting to multiple monitors.



## -see-also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_openadapterfromdevicename.md">D3DKMT_OPENADAPTERFROMDEVICENAME</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTOpenAdapterFromDeviceName function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

