---
UID: NE:d3dkmddi._DXGK_VIDPN_INTERFACE_VERSION
title: DXGK_VIDPN_INTERFACE_VERSION (d3dkmddi.h)
description: The DXGK_VIDPN_INTERFACE_VERSION enumeration indicates the version of a video present network (VidPN) interface.
old-location: display\dxgk_vidpn_interface_version.htm
ms.date: 02/28/2023
keywords: ["DXGK_VIDPN_INTERFACE_VERSION enumeration"]
ms.keywords: DXGK_VIDPN_INTERFACE_VERSION, DXGK_VIDPN_INTERFACE_VERSION enumeration [Display Devices], DXGK_VIDPN_INTERFACE_VERSION_UNINITIALIZED, DXGK_VIDPN_INTERFACE_VERSION_V1, DmEnums_69c4e28b-70fe-4576-b726-6fa6d78c97d0.xml, _DXGK_VIDPN_INTERFACE_VERSION, d3dkmddi/DXGK_VIDPN_INTERFACE_VERSION, d3dkmddi/DXGK_VIDPN_INTERFACE_VERSION_UNINITIALIZED, d3dkmddi/DXGK_VIDPN_INTERFACE_VERSION_V1, display.dxgk_vidpn_interface_version
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
req.typenames: DXGK_VIDPN_INTERFACE_VERSION
f1_keywords:
 - _DXGK_VIDPN_INTERFACE_VERSION
 - d3dkmddi/_DXGK_VIDPN_INTERFACE_VERSION
 - DXGK_VIDPN_INTERFACE_VERSION
 - d3dkmddi/DXGK_VIDPN_INTERFACE_VERSION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_VIDPN_INTERFACE_VERSION
 - DXGK_VIDPN_INTERFACE_VERSION
---

# DXGK_VIDPN_INTERFACE_VERSION enumeration

## -description

The **DXGK_VIDPN_INTERFACE_VERSION** enumeration indicates the version of a video present network (VidPN) interface.

## -enum-fields

### -field DXGK_VIDPN_INTERFACE_VERSION_UNINITIALIZED

Indicates that a variable of type DXGK_VIDPN_INTERFACE_VERSION has not yet been assigned a meaningful value.

### -field DXGK_VIDPN_INTERFACE_VERSION_V1

Indicates version 1 of the VidPN interface.

### -field DXGK_VIDPN_INTERFACE_VERSION_V2

Indicates version 2 of the VidPN interface.

## -remarks

The **VidPnInterfaceVersion** parameter of the [**DxgkCbQueryVidPnInterface**](nc-d3dkmddi-dxgkcb_queryvidpninterface.md) function and the **Version** member of the [**DXGK_VIDPN_INTERFACE**](ns-d3dkmddi-_dxgk_vidpn_interface.md) structure are DXGK_VIDPN_INTERFACE_VERSION values.

## -see-also

[VidPn Objects and Interfaces](/windows-hardware/drivers/display/vidpn-objects-and-interfaces)
