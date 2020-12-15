---
UID: NS:dispmprt._DXGKARG_GETDPADDRESS
title: DXGKARG_GETDPADDRESS
ms.date: 03/24/2020
ms.topic: language-reference
tech.root: display
targetos: Windows
description: The DXGKARG_GETDPADDRESS structure is a parameter for the DXGKDDI_GETDPADDRESS callback.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: dispmprt.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGKARG_GETDPADDRESS, *PDXGKARG_GETDPADDRESS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dispmprt.h
api_name:
 - _DXGKARG_GETDPADDRESS
 - DXGKARG_GETDPADDRESS
f1_keywords:
 - _DXGKARG_GETDPADDRESS
 - dispmprt/_DXGKARG_GETDPADDRESS
 - PDXGKARG_GETDPADDRESS
 - dispmprt/PDXGKARG_GETDPADDRESS
 - DXGKARG_GETDPADDRESS
 - dispmprt/DXGKARG_GETDPADDRESS
dev_langs:
 - c++
---

# DXGKARG_GETDPADDRESS structure


## -description

The **DXGKARG_GETDPADDRESS** structure is a parameter for the [**DXGKDDI_GETDPADDRESS**](nc-dispmprt-dxgkddi_getdpaddress.md) callback.

## -struct-fields

### -field TargetId

[**D3DDDI_VIDEO_PRESENT_TARGET_ID**](../d3dkmdt/ns-d3dkmdt-_d3dkmdt_video_present_target.md) structure that contains information about video present target.

### -field DPNativeError

Field in which the driver can encode more details about the error when returning STATUS_DEVICE_PROTOCOL_ERROR from [**DXGKDDI_GETDPADDRESS**](nc-dispmprt-dxgkddi_getdpaddress.md).

### -field RootPortIndex

Index value of the DP-capable connector.

### -field NumLinks

Number of links between the root port and target device. **NumLinks** should be **0** if the DP monitor is directly connected to the GPU.

### -field RelAddress

DP Relative Address. The format is described in the DP specification.

## -remarks

## -see-also

[**D3DDDI_VIDEO_PRESENT_TARGET_ID**](../d3dkmdt/ns-d3dkmdt-_d3dkmdt_video_present_target.md)

[**DXGKDDI_GETDPADDRESS**](nc-dispmprt-dxgkddi_getdpaddress.md)