---
UID: NE:d3dkmddi._DXGK_TDR_TYPE
tech.root: display
title: DXGK_TDR_TYPE
ms.date: 04/01/2024
targetos: Windows
description: Learn more about the DXGK_TDR_TYPE enumeration.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: d3dkmddi.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: false
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_TDR_TYPE
 - DXGK_TDR_TYPE
f1_keywords:
 - _DXGK_TDR_TYPE
 - d3dkmddi/_DXGK_TDR_TYPE
 - DXGK_TDR_TYPE
 - d3dkmddi/DXGK_TDR_TYPE
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGK_TDR_TYPE
---

# DXGK_TDR_TYPE enumeration (d3dkmddi.h)

## -description

The **DXGK_TDR_TYPE** enumeration specifies the type of timeout detection and recovery (TDR) event that occurred.

## -enum-fields

### -field DXGK_TDR_TYPE_UNKNOWN:0

Reserved. A KMD's [**DxgkDdiCollectDbgInfo2**](nc-d3dkmddi-dxgkddi_collectdbginfo2.md) implementation shouldn't receive this value.

### -field DXGK_TDR_TYPE_FORCED:1

The TDR is forced via [**D3DKMT_ESCAPE_TDRDBGCTRL**](../d3dkmthk/ns-d3dkmthk-_d3dkmt_escape.md) with zero data or with **D3DKMT_TDRDBGCTRLTYPE_FORCETDR** type.

### -field DXGK_TDR_TYPE_PREEMPT_TIMEOUT:2

For drivers that don't support engine reset, this value is used prior to resetting the whole adapter that had one of the GPU engines time out.

### -field DXGK_TDR_TYPE_VSYNC_TIMEOUT:3

This value is used when the display part of the GPU doesn't acknowledge a pending flip request in a timely manner.

### -field DXGK_TDR_TYPE_DOD_PRESENT_FORCED:4

This value is used for Display Only adapters when the TDR is forced via [**D3DKMT_TDRDBGCTRLTYPE_FORCEDODTDR**](../d3dkmthk/ne-d3dkmthk-_d3dkmt_tdrdbgctrltype.md) escape.

### -field DXGK_TDR_TYPE_DOD_PRESENT_TIMEOUT:5

This value is used for Display Only adapters when they don't complete a present within the TDR timeout.

### -field DXGK_TDR_TYPE_ENGINE_TIMEOUT:6

This value is used when a particular GPU engine can't complete pending GPU work or a preemption request within the TDR timeout.

### -field DXGK_TDR_TYPE_DOD_VSYNC_FORCED:7

This value is used for Display Only adapters when the TDR is forced via [**D3DKMT_TDRDBGCTRLTYPE_FORCEDODVSYNCTDR**](../d3dkmthk/ne-d3dkmthk-_d3dkmt_tdrdbgctrltype.md) escape.

### -field DXGK_TDR_TYPE_DOD_VSYNC_TIMEOUT:8

This value is used for Display Only adapters when they don't raise a VSync interrupt within the TDR timeout.

### -field DXGK_TDR_TYPE_ENGINE_TIMEOUT_PROMOTED:9

This value is used when a GPU engine timeout is promoted by the OS to the full adapter reset.

### -field DXGK_TDR_TYPE_PAGE_FAULT:10

This value is used when an adapter reset is requested by a GPU page fault interrupt that set the [**DXGK_PAGE_FAULT_ADAPTER_RESET_REQUIRED**](../d3dkmdt/ne-d3dkmdt-_dxgk_page_fault_flags.md) flag to 1.

### -field DXGK_TDR_TYPE_INVALID_FENCE:11

This value is used for certain legacy pre-WDDM 2.4 drivers when the GPU reports an incorrect submission or preempted fence value that results in a GPU reset.

### -field DXGK_TDR_TYPE_ENGINE_PAGE_FAULT:12

This value is used when a GPU engine reset is requested by a GPU page fault interrupt that set the [**DXGK_PAGE_FAULT_ENGINE_RESET_REQUIRED**](../d3dkmdt/ne-d3dkmdt-_dxgk_page_fault_flags.md) flag to 1.

### -field DXGK_TDR_TYPE_DISPLAY_ENGINE_FAULT:13

This value is used when a display engine fault is detected by the OS.

## -remarks

For more information, see [TDR debuggability improvements](/windows-hardware/drivers/display/tdr-debuggability-improvements).

## -see-also

[**DXGKARG_COLLECTDBGINFO2**](ns-d3dkmddi-dxgkarg_collectdbginfo2.md)

[**DxgkDdiCollectDbgInfo2**](nc-d3dkmddi-dxgkddi_collectdbginfo2.md)
