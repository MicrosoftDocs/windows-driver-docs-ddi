---
UID: NS:d3dkmddi._DXGKARG_COLLECTDBGINFO
title: _DXGKARG_COLLECTDBGINFO (d3dkmddi.h)
description: The DXGKARG_COLLECTDBGINFO structure describes information for a debug report.
old-location: display\dxgkarg_collectdbginfo.htm
ms.date: 05/10/2018
keywords: ["DXGKARG_COLLECTDBGINFO structure"]
ms.keywords: DXGKARG_COLLECTDBGINFO, DXGKARG_COLLECTDBGINFO structure [Display Devices], DmStructs_c3c19a4c-8536-474b-bca4-8b5af32fc4c8.xml, VIDEO_ENGINE_TIMEOUT_DETECTED, VIDEO_TDR_TIMEOUT_DETECTED, _DXGKARG_COLLECTDBGINFO, d3dkmddi/DXGKARG_COLLECTDBGINFO, display.dxgkarg_collectdbginfo
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
 - DXGKARG_COLLECTDBGINFO
---

# _DXGKARG_COLLECTDBGINFO structure


## -description

The DXGKARG_COLLECTDBGINFO structure describes information for a debug report.

## -struct-fields

### -field Reason

[in] The <a href="/windows-hardware/drivers/debugger/bug-check-code-reference2">bug-check code</a> for which to return debug information in the buffer that <b>pBuffer</b> points to. These are possible values:

| **Value** | **Meaning** | 
|:--|:--|
| **VIDEO_TDR_TIMEOUT_DETECTED** 0x117|A [DxgkDdiResetEngine](./nc-d3dkmddi-dxgkddi_resetengine.md)  operation has reset a logical adapter. |
| **VIDEO_ENGINE_TIMEOUT_DETECTED** 0x141|A [DxgkDdiResetEngine](./nc-d3dkmddi-dxgkddi_resetengine.md)  operation has reset one or more nodes within a physical adapter.
Available starting in Windows 8. |

### -field pBuffer

[out] A pointer to a buffer that receives the debug information that <b>Reason</b> specifies.

### -field BufferSize

[in] The maximum size, in bytes, to copy to the buffer that <b>pBuffer</b> points to.

### -field pExtension

[out] A pointer to a <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_collectdbginfo_ext">DXGKARG_COLLECTDBGINFO_EXT</a> structure that is allocated by the operating system and that the driver optionally populates with debug extension information.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_collectdbginfo_ext">DXGKARG_COLLECTDBGINFO_EXT</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_collectdbginfo">DxgkDdiCollectDbgInfo</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_resetengine">DxgkDdiResetEngine</a>
