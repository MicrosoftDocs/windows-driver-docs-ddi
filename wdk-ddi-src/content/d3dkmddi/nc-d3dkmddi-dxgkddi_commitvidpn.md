---
UID: NC:d3dkmddi.DXGKDDI_COMMITVIDPN
title: DXGKDDI_COMMITVIDPN (d3dkmddi.h)
description: Learn more about the DXGKDDI_COMMITVIDPN function.
ms.date: 03/15/2024
keywords: ["DXGKDDI_COMMITVIDPN callback function"]
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
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
req.irql: PASSIVE_LEVEL
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - DXGKDDI_COMMITVIDPN
 - d3dkmddi/DXGKDDI_COMMITVIDPN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_COMMITVIDPN
---

# DXGKDDI_COMMITVIDPN callback function

## -description

The **DxgkDdiCommitVidPn** function makes a specified video present network (VidPN) active on a display adapter.

## -parameters

### -param hAdapter

A handle to a context block associated with a display adapter. The display miniport driver previously provided this handle to the DirectX graphics kernel subsystem in the **MiniportDeviceContext** output parameter of the [**DxgkDdiAddDevice**](../dispmprt/nc-dispmprt-dxgkddi_add_device.md) function.

### -param pCommitVidPn

A pointer to a [**DXGKARG_COMMITVIDPN**](ns-d3dkmddi-_dxgkarg_commitvidpn.md) structure that contains function arguments.

## -returns

**DxgkDdiCommitVidPn** returns STATUS_SUCCESS upon successful completion; otherwise, it returns an appropriate NTSTATUS code such as STATUS_GRAPHICS_INVALID_VIDPN_TOPOLOGY.

## -remarks

For more information about how the display miniport driver should handle calls to **DxgkDdiCommitVidPn**, see [**DXGKARG_COMMITVIDPN**](ns-d3dkmddi-_dxgkarg_commitvidpn.md).

Beginning with Windows 8, if the display miniport driver sets the **SupportSmoothRotation** member of the [**DXGK_DRIVERCAPS**](ns-d3dkmddi-_dxgk_drivercaps.md) structure, it must support updating the path rotation on the adapter using the [**DxgkDdiUpdateActiveVidPnPresentPath**](nc-d3dkmddi-dxgkddi_updateactivevidpnpresentpath.md) function. The driver must always be able to set the path rotation during a call to the **DxgkDdiCommitVidPn** function.

## -see-also

[**DXGKARG_COMMITVIDPN**](ns-d3dkmddi-_dxgkarg_commitvidpn.md)

[**DXGK_DRIVERCAPS**](ns-d3dkmddi-_dxgk_drivercaps.md)

[**DxgkDdiAddDevice**](../dispmprt/nc-dispmprt-dxgkddi_add_device.md)

[**DxgkDdiUpdateActiveVidPnPresentPath**](nc-d3dkmddi-dxgkddi_updateactivevidpnpresentpath.md)
