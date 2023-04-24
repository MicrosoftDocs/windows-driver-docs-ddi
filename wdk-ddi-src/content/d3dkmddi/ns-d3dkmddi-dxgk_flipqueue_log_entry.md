---
UID: NS:d3dkmddi._DXGK_FLIPQUEUE_LOG_ENTRY
tech.root: display
title: DXGK_FLIPQUEUE_LOG_ENTRY
ms.date: 02/03/2023
targetos: Windows
description: Learn more about the DXGK_FLIPQUEUE_LOG_ENTRY structure.
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
req.target-min-winverclnt: Windows 11 (WDDM 3.0)
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGK_FLIPQUEUE_LOG_ENTRY
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_FLIPQUEUE_LOG_ENTRY
 - DXGK_FLIPQUEUE_LOG_ENTRY
f1_keywords:
 - _DXGK_FLIPQUEUE_LOG_ENTRY
 - d3dkmddi/_DXGK_FLIPQUEUE_LOG_ENTRY
 - DXGK_FLIPQUEUE_LOG_ENTRY
 - d3dkmddi/DXGK_FLIPQUEUE_LOG_ENTRY
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGK_FLIPQUEUE_LOG_ENTRY
---

## -description

In the [hardware flip queue model](/windows-hardware/drivers/display/hardware-flip-queue), the **DXGK_FLIPQUEUE_LOG_ENTRY** structure contains a single flip queue log entry for a completed or cancelled flip.

## -struct-fields

### -field PresentId

[in] Identifies the completed or cancelled flip.

### -field PresentTimestamp

[in] Time stamp of the flip. This value is specified in CPU clock counter units (obtained from obtained from [**KeQueryPerformanceCounter**](/windows-hardware/drivers/ddi/ntifs/nf-ntifs-kequeryperformancecounter)). **PresentTimestamp** can be one of the following values:

| Value | Meaning |
| ----- | ------- |
| **DXGK_HWFLIPQUEUE_TIMESTAMP_CANCELLED** | The flip was cancelled and contents were never displayed on the screen. |
| Value > 0 | The time stamp when the flip started being visible on the screen; that is, the scanout's start time. |

## -remarks

The [**DXGKARG_SETFLIPQUEUELOGBUFFER**](ns-d3dkmddi-dxgkarg_setflipqueuelogbuffer.md) structure contains a pointer to an array of **DXGK_FLIPQUEUE_LOG_ENTRY** structures.

## -see-also

[**DXGKARG_SETFLIPQUEUELOGBUFFER**](ns-d3dkmddi-dxgkarg_setflipqueuelogbuffer.md)

[**DXGKDDI_SETFLIPQUEUELOGBUFFER**](nc-d3dkmddi-dxgkddi_setflipqueuelogbuffer.md)
