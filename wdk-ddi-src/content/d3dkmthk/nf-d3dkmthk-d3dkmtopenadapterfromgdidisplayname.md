---
UID: NF:d3dkmthk.D3DKMTOpenAdapterFromGdiDisplayName
title: D3DKMTOpenAdapterFromGdiDisplayName function
author: windows-driver-content
description: The D3DKMTOpenAdapterFromGdiDisplayName function maps a GDI device name to a graphics adapter handle and, if the adapter contains multiple monitor outputs, to one of those outputs.
old-location: display\d3dkmtopenadapterfromgdidisplayname.htm
old-project: display
ms.assetid: 56656fc2-785c-4021-9864-e4c152551973
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMTOpenAdapterFromGdiDisplayName
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
req.alt-api: D3DKMTOpenAdapterFromGdiDisplayName
req.alt-loc: Gdi32.dll,API-MS-Win-DX-D3DKmt-l1-1-0.dll,API-MS-Win-DX-D3DKmt-l1-1-1.dll,API-MS-Win-DX-D3DKMT-L1-1-2.dll
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
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTOpenAdapterFromGdiDisplayName function



## -description
The <b>D3DKMTOpenAdapterFromGdiDisplayName</b> function maps a GDI device name to a graphics adapter handle and, if the adapter contains multiple monitor outputs, to one of those outputs.



## -syntax

````
NTSTATUS D3DKMTOpenAdapterFromGdiDisplayName(
  _Inout_ D3DKMT_OPENADAPTERFROMGDIDISPLAYNAME *pData
);
````


## -parameters

### -param pData [in, out]

 A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_openadapterfromgdidisplayname.md">D3DKMT_OPENADAPTERFROMGDIDISPLAYNAME</a> structure that describes the parameters that are required to perform the mapping.


## -returns
<b>D3DKMTOpenAdapterFromGdiDisplayName</b>
       returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The mapping was performed successfully.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>Parameters were validated and determined to be incorrect or the Windows Vista display driver model was not used.

 

This function might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.


## -remarks
A graphics adapter corresponds to a video card. A monitor output corresponds to a head on a video card. A system with a single video card contains only one adapter. However, if the video card supports multiple heads, it supports outputting to multiple monitors.


## -see-also
<dl>
<dt>
<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_openadapterfromgdidisplayname.md">D3DKMT_OPENADAPTERFROMGDIDISPLAYNAME</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTOpenAdapterFromGdiDisplayName function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

