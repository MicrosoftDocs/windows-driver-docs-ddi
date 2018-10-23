---
UID: NS:d3dkmthk._D3DKMT_DESTROYKEYEDMUTEX
title: "_D3DKMT_DESTROYKEYEDMUTEX"
author: windows-driver-content
description: The D3DKMT_DESTROYKEYEDMUTEX structure describes a keyed mutex that the D3DKMTDestroyKeyedMutex function destroys.
old-location: display\d3dkmt_destroykeyedmutex.htm
ms.assetid: b7903bf8-ef62-4224-a81d-4b41f36e2061
ms.date: 05/10/2018
ms.keywords: D3DKMT_DESTROYKEYEDMUTEX, D3DKMT_DESTROYKEYEDMUTEX structure [Display Devices], OpenGL_Structs_4eb8a9cb-d2b1-445b-b545-5ec0a017a61c.xml, _D3DKMT_DESTROYKEYEDMUTEX, d3dkmthk/D3DKMT_DESTROYKEYEDMUTEX, display.d3dkmt_destroykeyedmutex
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: D3DKMT_DESTROYKEYEDMUTEX is supported beginning with the Windows 7 operating system.
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
-	D3DKMT_DESTROYKEYEDMUTEX
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_DESTROYKEYEDMUTEX
---

# _D3DKMT_DESTROYKEYEDMUTEX structure


## -description


The D3DKMT_DESTROYKEYEDMUTEX structure describes a keyed mutex that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546920">D3DKMTDestroyKeyedMutex</a> function destroys. 


## -struct-fields




### -field hKeyedMutex

[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the keyed mutex object to destroy. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546920">D3DKMTDestroyKeyedMutex</a>
 

 

