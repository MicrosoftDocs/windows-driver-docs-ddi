---
UID: NS:d3dkmddi._DXGKARG_COMMITVIDPN
title: DXGKARG_COMMITVIDPN (d3dkmddi.h)
description: Learn more about the DXGKARG_COMMITVIDPN structure.
ms.date: 03/15/2024
keywords: ["DXGKARG_COMMITVIDPN structure"]
req.header: d3dkmddi.h
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
req.typenames: DXGKARG_COMMITVIDPN
f1_keywords:
 - _DXGKARG_COMMITVIDPN
 - d3dkmddi/_DXGKARG_COMMITVIDPN
 - DXGKARG_COMMITVIDPN
 - d3dkmddi/DXGKARG_COMMITVIDPN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARG_COMMITVIDPN
 - DXGKARG_COMMITVIDPN
---

# DXGKARG_COMMITVIDPN structure

## -description

The **DXGKARG_COMMITVIDPN** structure holds arguments for the [**DxgkDdiCommitVidPn**](nc-d3dkmddi-dxgkddi_commitvidpn.md) function.

## -struct-fields

### -field hFunctionalVidPn

A handle to a functional VidPN object that is to be made active on the display adapter.

### -field AffectedVidPnSourceId

The constant D3DDDI_ID_ALL or the identifier of a particular video present source in the VidPN:

* If this member is a source identifier, **DxgkDdiCommitVidPn** updates only the modes of the video present paths that originate at that source. **DxgkDdiCommitVidPn** doesn't need to inspect paths that originate from other sources because those paths are the same in the new VidPN as they are in the currently active VidPN.
* If this member is equal to D3DDDI_ID_ALL, **DxgkDdiCommitVidPn** must inspect and update the entire VidPN as a single transaction; that is, the entire new VidPN must be made active or the entire current VidPN must remain active.

### -field MonitorConnectivityChecks

A [**D3DKMDT_MONITOR_CONNECTIVITY_CHECKS**](../d3dkmdt/ne-d3dkmdt-_d3dkmdt_monitor_connectivity_checks.md) enumerator (**D3DKMDT_MCC_IGNORE** or **D3DKMDT_MCC_ENFORCE**) that specifies whether to verify that video outputs in the new topology have monitors connected:

* If this member is equal to **D3DKMDT_MCC_ENFORCE** and one of the video outputs in the new VidPN's topology doesn't have a monitor connected, **DxgkDdiCommitVidPn** must leave the currently active VidPN in place and return STATUS_GRAPHICS_INVALID_VIDPN_TOPOLOGY.
* If this member is equal to **D3DKMDT_MCC_IGNORE**, **DxgkDdiCommitVidPn** can make the new VidPN active without checking to see whether any video outputs have monitors connected.

### -field hPrimaryAllocation

A handle to the primary allocation associated with the video present source identified by **AffectedVidPnSourceId**.

### -field Flags [in]

A [**DXGKARG_COMMITVIDPN_FLAGS**](ns-d3dkmddi-_dxgkarg_commitvidpn_flags.md) structure that identifies details about a call to the [**DxgkDdiCommitVidPn**](nc-d3dkmddi-dxgkddi_commitvidpn.md) function.

## -remarks

The D3DDDI_ID_ALL constant is defined in *D3dukmddi.h*.

## -see-also

[**D3DKMDT_MONITOR_CONNECTIVITY_CHECKS**](../d3dkmdt/ne-d3dkmdt-_d3dkmdt_monitor_connectivity_checks.md)

[**DxgkDdiCommitVidPn**](nc-d3dkmddi-dxgkddi_commitvidpn.md)
