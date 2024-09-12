---
UID: NS:d3dkmdt._DXGK_ADAPTER_PERFDATACAPS
title: DXGK_ADAPTER_PERFDATACAPS (d3dkmdt.h)
description: Learn more about the DXGK_ADAPTER_PERFDATACAPS structure.
ms.date: 09/11/2024
req.header: d3dkmdt.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: DXGK_ADAPTER_PERFDATACAPS
targetos: Windows
tech.root: display
f1_keywords:
 - _DXGK_ADAPTER_PERFDATACAPS
 - d3dkmdt/_DXGK_ADAPTER_PERFDATACAPS
 - DXGK_ADAPTER_PERFDATACAPS
 - d3dkmdt/DXGK_ADAPTER_PERFDATACAPS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmdt.h
api_name:
 - _DXGK_ADAPTER_PERFDATACAPS
 - DXGK_ADAPTER_PERFDATACAPS
---

# DXGK_ADAPTER_PERFDATACAPS structure

## -description

The **DXGK_ADAPTER_PERFDATACAPS** structure describes the performance data capabilities of the adapter.

## -struct-fields

### -field MaxMemoryBandwidth

The maximum memory bandwidth in bytes for 1 second.

### -field MaxPCIEBandwidth

The maximum PCIE bandwidth in bytes for 1 second.

### -field MaxFanRPM

The maximum fan revolutions per minute of the main fan.

### -field TemperatureMax

The maximum temperature before damage levels occur in deci-Celsius (a value of 1 = 0.1C).

### -field TemperatureWarning

The temperature level where temperature based throttling begins in deci-Celsius (a value of 1 = 0.1C).

## -remarks

KMD's [**DxgkDdiQueryAdapterInfo**](../d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo.md) function should fill in the **DXGK_ADAPTER_PERFDATACAPS** structure in response to a [**DXGK_QUERYADAPTERINFOTYPE**](../d3dkmddi/ne-d3dkmddi-_dxgk_queryadapterinfotype.md) query of type **DXGKQAITYPE_ADAPTERPERFDATA_CAPS**.

## -see-also

[**DXGK_QUERYADAPTERINFOTYPE**](../d3dkmddi/ne-d3dkmddi-_dxgk_queryadapterinfotype.md)

[**DxgkDdiQueryAdapterInfo**](../d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo.md)
