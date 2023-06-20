---
UID: NE:d3dkmddi._DXGK_MONITOR_INTERFACE_VERSION
title: DXGK_MONITOR_INTERFACE_VERSION (d3dkmddi.h)
description: Learn more about the DXGK_MONITOR_INTERFACE_VERSION enumeration.
ms.date: 06/09/2023
keywords: ["DXGK_MONITOR_INTERFACE_VERSION enumeration"]
ms.keywords: DXGK_MONITOR_INTERFACE_VERSION, DXGK_MONITOR_INTERFACE_VERSION enumeration [Display Devices], DXGK_MONITOR_INTERFACE_VERSION_UNINITIALIZED, DXGK_MONITOR_INTERFACE_VERSION_V1, DXGK_MONITOR_INTERFACE_VERSION_V2, DmEnums_4ec3a10c-c04f-431b-851d-908a5ff972a1.xml, _DXGK_MONITOR_INTERFACE_VERSION, d3dkmddi/DXGK_MONITOR_INTERFACE_VERSION, d3dkmddi/DXGK_MONITOR_INTERFACE_VERSION_UNINITIALIZED, d3dkmddi/DXGK_MONITOR_INTERFACE_VERSION_V1, d3dkmddi/DXGK_MONITOR_INTERFACE_VERSION_V2, display.dxgk_monitor_interface_version
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
req.typenames: DXGK_MONITOR_INTERFACE_VERSION
f1_keywords:
 - _DXGK_MONITOR_INTERFACE_VERSION
 - d3dkmddi/_DXGK_MONITOR_INTERFACE_VERSION
 - DXGK_MONITOR_INTERFACE_VERSION
 - d3dkmddi/DXGK_MONITOR_INTERFACE_VERSION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_MONITOR_INTERFACE_VERSION
 - DXGK_MONITOR_INTERFACE_VERSION
---

# DXGK_MONITOR_INTERFACE_VERSION enumeration

## -description

The **DXGK_MONITOR_INTERFACE_VERSION** enumeration indicates a particular version of the [monitor interface](ns-d3dkmddi-_dxgk_monitor_interface.md).

## -enum-fields

### -field DXGK_MONITOR_INTERFACE_VERSION_UNINITIALIZED:0

Indicates that a variable of type **DXGK_MONITOR_INTERFACE_VERSION** has not yet been assigned a meaningful value.

### -field DXGK_MONITOR_INTERFACE_VERSION_V1:1

Indicates version 1, available in Windows Vista.

### -field DXGK_MONITOR_INTERFACE_VERSION_V2:2

Indicates version 2, available starting in Windows 7.

## -remarks

The **Version** member of the [**DXGK_MONITOR_INTERFACE**](ns-d3dkmddi-_dxgk_monitor_interface.md) structure is a value from the **DXGK_MONITOR_INTERFACE_VERSION** enumeration.
