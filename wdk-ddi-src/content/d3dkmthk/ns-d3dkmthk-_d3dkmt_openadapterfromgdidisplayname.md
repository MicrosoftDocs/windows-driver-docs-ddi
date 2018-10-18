---
UID: NS:d3dkmthk._D3DKMT_OPENADAPTERFROMGDIDISPLAYNAME
title: "_D3DKMT_OPENADAPTERFROMGDIDISPLAYNAME"
author: windows-driver-content
description: The D3DKMT_OPENADAPTERFROMGDIDISPLAYNAME structure describes the mapping of the given name of a GDI device to a graphics adapter handle and monitor output.
old-location: display\d3dkmt_openadapterfromgdidisplayname.htm
ms.assetid: 8b166fbb-f6fa-4d90-9b32-40ce213cbd71
ms.date: 5/10/2018
ms.keywords: D3DKMT_OPENADAPTERFROMGDIDISPLAYNAME, D3DKMT_OPENADAPTERFROMGDIDISPLAYNAME structure [Display Devices], OpenGL_Structs_a6a0807b-454b-48a4-91d1-26d62e592280.xml, _D3DKMT_OPENADAPTERFROMGDIDISPLAYNAME, d3dkmthk/D3DKMT_OPENADAPTERFROMGDIDISPLAYNAME, display.d3dkmt_openadapterfromgdidisplayname
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmthk.h
api_name:
-	D3DKMT_OPENADAPTERFROMGDIDISPLAYNAME
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_OPENADAPTERFROMGDIDISPLAYNAME
---

# _D3DKMT_OPENADAPTERFROMGDIDISPLAYNAME structure


## -description


The D3DKMT_OPENADAPTERFROMGDIDISPLAYNAME structure describes the mapping of the given name of a GDI device to a graphics adapter handle and monitor output.


## -struct-fields




### -field DeviceName

[in] A Unicode string that contains the name of the GDI device from which to open an adapter instance. 


### -field hAdapter

[out] A handle to the graphics adapter for the GDI device that <b>DeviceName</b> specifies. The adapter handle is returned from the call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547038">D3DKMTOpenAdapterFromGdiDisplayName</a> function.


### -field AdapterLuid

[out] The locally unique identifier (<a href="https://msdn.microsoft.com/library/windows/hardware/ff557080">LUID</a>) of the graphics adapter for the GDI device that <b>DeviceName</b> specifies. The LUID is returned from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547038">D3DKMTOpenAdapterFromGdiDisplayName</a> call.


### -field VidPnSourceId

[out] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology for the GDI device that <b>DeviceName</b> specifies. The identification number is returned from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547038">D3DKMTOpenAdapterFromGdiDisplayName</a> call.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547038">D3DKMTOpenAdapterFromGdiDisplayName</a>
 

 

