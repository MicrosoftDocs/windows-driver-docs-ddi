---
UID: NS:d3dumddi._DXVAHDDDI_FILTER_RANGE_DATA
title: _DXVAHDDDI_FILTER_RANGE_DATA (d3dumddi.h)
description: Describes a filter range.
old-location: display\dxvahdddi_filter_range_data.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["DXVAHDDDI_FILTER_RANGE_DATA structure"]
ms.keywords: DXVA2_Structs_6fe6de36-4bbb-4409-817e-52e6598363e6.xml, DXVAHDDDI_FILTER_RANGE_DATA, DXVAHDDDI_FILTER_RANGE_DATA structure [Display Devices], _DXVAHDDDI_FILTER_RANGE_DATA, d3dumddi/DXVAHDDDI_FILTER_RANGE_DATA, display.dxvahdddi_filter_range_data
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_FILTER_RANGE_DATA is supported beginning with the Windows 7 operating system.
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
req.typenames: DXVAHDDDI_FILTER_RANGE_DATA
f1_keywords:
 - _DXVAHDDDI_FILTER_RANGE_DATA
 - d3dumddi/_DXVAHDDDI_FILTER_RANGE_DATA
 - DXVAHDDDI_FILTER_RANGE_DATA
 - d3dumddi/DXVAHDDDI_FILTER_RANGE_DATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - DXVAHDDDI_FILTER_RANGE_DATA
---

# _DXVAHDDDI_FILTER_RANGE_DATA structure

## -description

The **DXVAHDDDI_FILTER_RANGE_DATA** structure describes a filter range.

## -struct-fields

### -field Minimum

[in] An **INT** that specifies the minimum value in the filter range.

### -field Maximum

[in] An **INT** that specifies the maximum value in the filter range.

### -field Default

[in] An **INT** that specifies the default value for the filter range.

### -field Multiplier

[in] A **FLOAT** value that specifies a multiplier to calculate the actual filter value.

## -remarks

A hue ProcAmp filter that is defined from –180.0 to 180.0 at 0.25 step size with a default value of 0.0 has the members of the **DXVAHDDDI_FILTER_RANGE_DATA** structure set to the following values, which are normalized by an implicit step size of 1:

* **Minimum** = –720
* **Maximum** = 720
* **Default** = 0
* **Multiplier** = 0.25
