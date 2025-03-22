---
UID: NS:d3dkmddi._DXGKARG_COLLECTDBGINFO2
tech.root: display
title: DXGKARG_COLLECTDBGINFO2
ms.date: 04/01/2024
targetos: Windows
description: Learn more about the DXGKARG_COLLECTDBGINFO2 structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2) 
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGKARG_COLLECTDBGINFO2
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARG_COLLECTDBGINFO2
 - DXGKARG_COLLECTDBGINFO2
f1_keywords:
 - _DXGKARG_COLLECTDBGINFO2
 - d3dkmddi/_DXGKARG_COLLECTDBGINFO2
 - DXGKARG_COLLECTDBGINFO2
 - d3dkmddi/DXGKARG_COLLECTDBGINFO2
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGKARG_COLLECTDBGINFO2
---

# DXGKARG_COLLECTDBGINFO2 structure (d3dkmddi.h)

## -description

The **DXGKARG_COLLECTDBGINFO** structure describes information for a debug report when [**DxgkDdiCollectDbgInfo2**](nc-d3dkmddi-dxgkddi_collectdbginfo2.md) is called.

## -struct-fields

### -field Reason

[in] The [bug-check code](/windows-hardware/drivers/debugger/bug-check-code-reference2) for which to return debug information in the buffer that **pBuffer** points to. These are possible values:

| Value | Meaning |
| ----- | ------- |
| **VIDEO_TDR_TIMEOUT_DETECTED** 0x117|A [**DxgkDdiResetEngine**](nc-d3dkmddi-dxgkddi_resetengine.md) operation has reset a logical adapter. |
| **VIDEO_ENGINE_TIMEOUT_DETECTED** 0x141|A [**DxgkDdiResetEngine**](nc-d3dkmddi-dxgkddi_resetengine.md) operation has reset one or more nodes within a physical adapter. Available starting in Windows 8. |

### -field pBuffer

[out] A pointer to a buffer that receives the debug information for the reason that **Reason** specifies.

### -field BufferSize

The maximum size, in bytes, to copy to the buffer that **pBuffer** points to.

### -field pExtension

A pointer to an OS-allocated [**DXGKARG_COLLECTDBGINFO_EXT**](ns-d3dkmddi-_dxgkarg_collectdbginfo_ext.md) structure that the driver optionally populates with debug extension information.

### -field TdrType

[in] A [**DXGK_TDR_TYPE**](ne-d3dkmddi-dxgk_tdr_type.md) value that specifies the type of TDR that occurred.

### -field TdrPayloadSize

[in] The size, in bytes, of the TDR payload that **TdrPayload** points to.

### -field TdrPayload

[in] A pointer to a buffer that contains the payload specific to certain **TdrType** values, as indicated the following table. This buffer can be NULL.

| TdrType | Associated structure |
| ------- | -------------------- |
| DXGK_TDR_TYPE_ENGINE_TIMEOUT | **TdrPayload** points to a [**DXGK_TDR_PAYLOAD_ENGINE_TIMEOUT**](ns-d3dkmddi-dxgk_tdr_payload_engine_timeout.md) structure. |
| DXGK_TDR_TYPE_VSYNC_TIMEOUT | **TdrPayload** points to a [**DXGK_TDR_PAYLOAD_VSYNC_TIMEOUT**](ns-d3dkmddi-dxgk_tdr_payload_vsync_timeout.md) structure. |

## -remarks

The layout of **DXGKARG_COLLECTDBGINFO2** is backwards compatible with [**DXGKARG_COLLECTDBGINFO**](ns-d3dkmddi-_dxgkarg_collectdbginfo.md) to allow the [**DxgkDdiCollectDbgInfo2**](nc-d3dkmddi-dxgkddi_collectdbginfo2.md) implementation to re-use existing [**DxgkDdiCollectDbgInfo**](nc-d3dkmddi-dxgkddi_collectdbginfo.md) helpers as needed. For this reason, the **Reason**, **pBuffer**, **BufferSize**, and **pExtension** fields have the same semantics.

For some TDR types (specified in **TdrType**), the OS provides additional information in the **TdrPayload** buffer of **TdrPayloadSize** bytes. It can be NULL, and the driver is expected to handle this case without crashing.

When the payload isn't NULL, it can be cast to a structure that corresponds to the TDR type. The OS might grow these structures in a backwards compatible manner, adding new fields at the end. The driver must check **TdrPayloadSize** prior to accessing **TdrPayload** fields to make sure the OS implements the desired payload version or later.

Memory that **TdrPayload** points to is only valid for the duration of the [**DxgkddiCollectDbgInfo2**](nc-d3dkmddi-dxgkddi_collectdbginfo2.md) call. The driver shouldn't store a pointer to **TdrPayload** past the end of **DxgkddiCollectDbgInfo2** call.

For more information, see [TDR debuggability improvements](/windows-hardware/drivers/display/tdr-debuggability-improvements).

## -see-also

[**DXGK_TDR_TYPE**](ne-d3dkmddi-dxgk_tdr_type.md)

[**DxgkDdiCollectDbgInfo**](nc-d3dkmddi-dxgkddi_collectdbginfo.md)

[**DxgkDdiCollectDbgInfo2**](nc-d3dkmddi-dxgkddi_collectdbginfo2.md)
