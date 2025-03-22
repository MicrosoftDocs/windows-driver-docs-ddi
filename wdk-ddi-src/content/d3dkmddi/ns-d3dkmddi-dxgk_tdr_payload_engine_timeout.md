---
UID: NS:d3dkmddi._DXGK_TDR_PAYLOAD_ENGINE_TIMEOUT
tech.root: display
title: DXGK_TDR_PAYLOAD_ENGINE_TIMEOUT
ms.date: 04/01/2024
targetos: Windows
description: Learn more about the DXGK_TDR_PAYLOAD_ENGINE_TIMEOUT structure.
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
req.typenames: DXGK_TDR_PAYLOAD_ENGINE_TIMEOUT
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
 - _DXGK_TDR_PAYLOAD_ENGINE_TIMEOUT
 - DXGK_TDR_PAYLOAD_ENGINE_TIMEOUT
f1_keywords:
 - _DXGK_TDR_PAYLOAD_ENGINE_TIMEOUT
 - d3dkmddi/_DXGK_TDR_PAYLOAD_ENGINE_TIMEOUT
 - DXGK_TDR_PAYLOAD_ENGINE_TIMEOUT
 - d3dkmddi/DXGK_TDR_PAYLOAD_ENGINE_TIMEOUT
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGK_TDR_PAYLOAD_ENGINE_TIMEOUT
---

# DXGK_TDR_PAYLOAD_ENGINE_TIMEOUT structure (d3dkmddi.h)

## -description

The **DXGK_TDR_PAYLOAD_ENGINE_TIMEOUT** structure contains the payload for a [**DxgkDdiCollectDbgInfo2**](nc-d3dkmddi-dxgkddi_collectdbginfo2.md) call when **TdrType** is **DXGK_TDR_TYPE_ENGINE_TIMEOUT**.

## -struct-fields

### -field NodeOrdinal

[in] Node ordinal for the engine being reset.

### -field EngineOrdinal

[in] Engine ordinal for the engine being reset.

### -field LastHwCompletedFenceId

[in] For engines not using the hardware scheduling model, the last fence ID completed by the GPU.

### -field LastHwSubmittedFenceId

[in] For engines not using the hardware scheduling model, the last fence ID submitted to the GPU.

### -field NumberOfPendingSuspendRequests

[in] For engines using the hardware scheduling model, the number of outstanding context suspend requests at the time of the TDR.

### -field NumberOfReadyInteractiveHwQueues

[in] For engines using the hardware scheduling model, the number of ready interactive hardware queues in flight at the time of the TDR.

### -field hContext

[out] Handle of the context that KMD believes has timed out. If KMD couldn't reliably determine which text timed out, it should leave **hContext** set to NULL.

## -remarks

For more information, see [TDR debuggability improvements](/windows-hardware/drivers/display/tdr-debuggability-improvements).

## -see-also

[**DXGK_TDR_TYPE**](ne-d3dkmddi-dxgk_tdr_type.md)

[**DXGKARG_COLLECTDBGINFO2**](ns-d3dkmddi-dxgkarg_collectdbginfo2.md)

[**DxgkDdiCollectDbgInfo2**](nc-d3dkmddi-dxgkddi_collectdbginfo2.md)
