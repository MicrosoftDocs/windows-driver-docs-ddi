---
UID: NS:d3dkmddi._DXGKARG_COLLECTDBGINFO
title: DXGKARG_COLLECTDBGINFO (d3dkmddi.h)
description: Learn more about the DXGKARG_COLLECTDBGINFO structure.
ms.date: 04/01/2024
keywords: ["DXGKARG_COLLECTDBGINFO structure"]
req.header: d3dkmddi.h
req.construct-type: structure
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista
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
req.typenames: DXGKARG_COLLECTDBGINFO
f1_keywords:
 - _DXGKARG_COLLECTDBGINFO
 - d3dkmddi/_DXGKARG_COLLECTDBGINFO
 - DXGKARG_COLLECTDBGINFO
 - d3dkmddi/DXGKARG_COLLECTDBGINFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARG_COLLECTDBGINFO
 - DXGKARG_COLLECTDBGINFO
---

# DXGKARG_COLLECTDBGINFO structure (d3dkmddi.h)



## -description

The **DXGKARG_COLLECTDBGINFO** structure describes information for a debug report.

## -struct-fields

### -field Reason [in]

The [bug-check code](/windows-hardware/drivers/debugger/bug-check-code-reference2) for which to return debug information in the buffer that **pBuffer** points to. These are possible values:

| Value | Meaning |
| ----- | ------- |
| **VIDEO_TDR_TIMEOUT_DETECTED** 0x117|A [**DxgkDdiResetEngine**](nc-d3dkmddi-dxgkddi_resetengine.md) operation has reset a logical adapter. |
| **VIDEO_ENGINE_TIMEOUT_DETECTED** 0x141|A [**DxgkDdiResetEngine**](nc-d3dkmddi-dxgkddi_resetengine.md) operation has reset one or more nodes within a physical adapter. Available starting in Windows 8. |

### -field pBuffer [out]

A pointer to a buffer that receives the debug information for the reason that **Reason** specifies.

### -field BufferSize [in]

The maximum size, in bytes, to copy to the buffer that **pBuffer** points to.

### -field pExtension [out]

A pointer to an OS-allocated [**DXGKARG_COLLECTDBGINFO_EXT**](ns-d3dkmddi-_dxgkarg_collectdbginfo_ext.md) structure that the driver optionally populates with debug extension information.

## -remarks

See [**DxgkDdiCollectDbgInfo2**](nc-d3dkmddi-dxgkddi_collectdbginfo2.md) for extended TDR debug information.

## -see-also

[**DXGKARG_COLLECTDBGINFO_EXT**](ns-d3dkmddi-_dxgkarg_collectdbginfo_ext.md)

[**DxgkDdiCollectDbgInfo**](nc-d3dkmddi-dxgkddi_collectdbginfo.md)

[**DxgkDdiCollectDbgInfo2**](nc-d3dkmddi-dxgkddi_collectdbginfo2.md)

[**DxgkDdiResetEngine**](nc-d3dkmddi-dxgkddi_resetengine.md)
