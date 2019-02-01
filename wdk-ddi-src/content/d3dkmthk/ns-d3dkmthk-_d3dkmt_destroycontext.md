---
UID: NS:d3dkmthk._D3DKMT_DESTROYCONTEXT
title: _D3DKMT_DESTROYCONTEXT (d3dkmthk.h)
description: The D3DKMT_DESTROYCONTEXT structure contains a handle to a kernel-mode device context to release.
old-location: display\d3dkmt_destroycontext.htm
ms.assetid: 116c0fa7-ac3c-4a56-804c-637514a19c73
ms.date: 05/10/2018
ms.keywords: D3DKMT_DESTROYCONTEXT, D3DKMT_DESTROYCONTEXT structure [Display Devices], OpenGL_Structs_97f52665-09e6-4f11-b2cc-a7abcc61827c.xml, _D3DKMT_DESTROYCONTEXT, d3dkmthk/D3DKMT_DESTROYCONTEXT, display.d3dkmt_destroycontext
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
-	D3DKMT_DESTROYCONTEXT
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_DESTROYCONTEXT
---

# _D3DKMT_DESTROYCONTEXT structure


## -description


The D3DKMT_DESTROYCONTEXT structure contains a handle to a kernel-mode device context to release.


## -struct-fields




### -field hContext

[in] A handle to the device context that the Microsoft DirectX graphics kernel subsystem (<i>Dxgkrnl.sys</i>) supplied and that is returned from the call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546814">D3DKMTCreateContext</a> function.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546814">D3DKMTCreateContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546897">D3DKMTDestroyContext</a>
 

 

