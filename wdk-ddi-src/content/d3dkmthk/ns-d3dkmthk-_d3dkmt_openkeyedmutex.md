---
UID: NS:d3dkmthk._D3DKMT_OPENKEYEDMUTEX
title: _D3DKMT_OPENKEYEDMUTEX (d3dkmthk.h)
description: The D3DKMT_OPENKEYEDMUTEX structure describes a keyed mutex that the D3DKMTOpenKeyedMutex function opens.
old-location: display\d3dkmt_openkeyedmutex.htm
ms.date: 05/10/2018
keywords: ["D3DKMT_OPENKEYEDMUTEX structure"]
ms.keywords: D3DKMT_OPENKEYEDMUTEX, D3DKMT_OPENKEYEDMUTEX structure [Display Devices], OpenGL_Structs_78a96126-b992-431f-9e91-c08c61694732.xml, _D3DKMT_OPENKEYEDMUTEX, d3dkmthk/D3DKMT_OPENKEYEDMUTEX, display.d3dkmt_openkeyedmutex
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: D3DKMT_OPENKEYEDMUTEX is supported beginning with the Windows 7 operating system.
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
req.typenames: D3DKMT_OPENKEYEDMUTEX
f1_keywords:
 - _D3DKMT_OPENKEYEDMUTEX
 - d3dkmthk/_D3DKMT_OPENKEYEDMUTEX
 - D3DKMT_OPENKEYEDMUTEX
 - d3dkmthk/D3DKMT_OPENKEYEDMUTEX
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_OPENKEYEDMUTEX
 - D3DKMT_OPENKEYEDMUTEX
---

# _D3DKMT_OPENKEYEDMUTEX structure


## -description

The D3DKMT_OPENKEYEDMUTEX structure describes a keyed mutex that the <a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtopenkeyedmutex">D3DKMTOpenKeyedMutex</a> function opens.

## -struct-fields

### -field hSharedHandle

[in] A D3DKMT_HANDLE data type that represents a kernel-mode shared global handle to the keyed mutex object.

### -field hKeyedMutex

[out] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the keyed mutex object in the current process.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtopenkeyedmutex">D3DKMTOpenKeyedMutex</a>

