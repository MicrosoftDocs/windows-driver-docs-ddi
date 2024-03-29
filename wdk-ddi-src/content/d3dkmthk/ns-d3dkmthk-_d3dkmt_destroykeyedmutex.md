---
UID: NS:d3dkmthk._D3DKMT_DESTROYKEYEDMUTEX
title: _D3DKMT_DESTROYKEYEDMUTEX (d3dkmthk.h)
description: The D3DKMT_DESTROYKEYEDMUTEX structure describes a keyed mutex that the D3DKMTDestroyKeyedMutex function destroys.
old-location: display\d3dkmt_destroykeyedmutex.htm
ms.date: 05/10/2018
keywords: ["D3DKMT_DESTROYKEYEDMUTEX structure"]
ms.keywords: D3DKMT_DESTROYKEYEDMUTEX, D3DKMT_DESTROYKEYEDMUTEX structure [Display Devices], OpenGL_Structs_4eb8a9cb-d2b1-445b-b545-5ec0a017a61c.xml, _D3DKMT_DESTROYKEYEDMUTEX, d3dkmthk/D3DKMT_DESTROYKEYEDMUTEX, display.d3dkmt_destroykeyedmutex
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
targetos: Windows
tech.root: display
req.typenames: D3DKMT_DESTROYKEYEDMUTEX
f1_keywords:
 - _D3DKMT_DESTROYKEYEDMUTEX
 - d3dkmthk/_D3DKMT_DESTROYKEYEDMUTEX
 - D3DKMT_DESTROYKEYEDMUTEX
 - d3dkmthk/D3DKMT_DESTROYKEYEDMUTEX
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_DESTROYKEYEDMUTEX
 - D3DKMT_DESTROYKEYEDMUTEX
---

# _D3DKMT_DESTROYKEYEDMUTEX structure


## -description

The D3DKMT_DESTROYKEYEDMUTEX structure describes a keyed mutex that the <a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtdestroykeyedmutex">D3DKMTDestroyKeyedMutex</a> function destroys.

## -struct-fields

### -field hKeyedMutex [in]

A D3DKMT_HANDLE data type that represents a kernel-mode handle to the keyed mutex object to destroy.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtdestroykeyedmutex">D3DKMTDestroyKeyedMutex</a>

