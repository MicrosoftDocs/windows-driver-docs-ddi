---
UID: NS:d3dkmthk._D3DKMT_ADAPTER_PERFDATA
title: _D3DKMT_ADAPTER_PERFDATA (d3dkmthk.h)
description: Contains input arguments for the D3DKMTQueryAdapterInfo function. Represents performance data collected per adapter on an interval basis.
ms.date: 10/19/2018
keywords: ["D3DKMT_ADAPTER_PERFDATA structure"]
ms.keywords: _D3DKMT_ADAPTER_PERFDATA, D3DKMT_ADAPTER_PERFDATA,
req.header: d3dkmthk.h
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
req.typenames: D3DKMT_ADAPTER_PERFDATA
targetos: Windows
tech.root: display
f1_keywords:
 - _D3DKMT_ADAPTER_PERFDATA
 - d3dkmthk/_D3DKMT_ADAPTER_PERFDATA
 - D3DKMT_ADAPTER_PERFDATA
 - d3dkmthk/D3DKMT_ADAPTER_PERFDATA
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_ADAPTER_PERFDATA
product:
 - Windows
---

# _D3DKMT_ADAPTER_PERFDATA structure


## -description

Contains input arguments for the [D3DKMTQueryAdapterInfo](nf-d3dkmthk-d3dkmtqueryadapterinfo.md) function. Represents performance data collected per adapter on an interval basis.

## -struct-fields

### -field PhysicalAdapterIndex

The physical adapter index in the LDA (linked display adapter) chain.

### -field MemoryFrequency

Clock frequency of the memory, represented in hertz.

### -field MaxMemoryFrequency

Max clock frequency of the memory while not overclocked, represented in hertz.

### -field MaxMemoryFrequencyOC

Max clock frequency of the memory while overclocked, represented in hertz.

### -field MemoryBandwidth

– Amount of total memory transferred in bytes.

### -field PCIEBandwidth

Amount of total memory transferred over the PCIE in bytes.

### -field FanRPM

The current rpm of the main fan.

### -field Power

The current power draw of the adapter in tenths of percentage, 1 = 0.1%.

### -field Temperature

The main temperature sensors reading in decimal Celsius. 1 = 0.1C.

### -field PowerStateOverride

Reports if the GPU is powered on with 1 otherwise it is 0.

