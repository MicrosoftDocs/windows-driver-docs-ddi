---
UID: NS:d3dkmthk._D3DKMT_NODE_PERFDATA
title: _D3DKMT_NODE_PERFDATA (d3dkmthk.h)
description: Represents performance data collected per engine from an adapter on an interval basis.
ms.assetid: 90d91283-4891-4459-b182-40bf600c8b92
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: _D3DKMT_NODE_PERFDATA, D3DKMT_NODE_PERFDATA,
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
req.typenames: D3DKMT_NODE_PERFDATA
topic_type:
- apiref
api_type:
- HeaderDef
api_location:
- d3dkmthk.h
api_name:
- _D3DKMT_NODE_PERFDATA
product: 
- Windows
targetos: Windows
tech.root: display
---

# _D3DKMT_NODE_PERFDATA structure

## -description

Represents performance data collected per engine from an adapter on an interval basis.

## -struct-fields

### -field NodeOrdinal

[in] Node ordinal of the requested engine.

### -field PhysicalAdapterIndex

[in] The physical adapter index in the LDA (linked display adapter) chain.

### -field Frequency

[out] Clock frequency of the requested engine, represented in hertz.

### -field MaxFrequency

[out] The max frequency the engine can normally reach in hertz while not overclocked.

### -field MaxFrequencyOC

[out] The max frequency the engine can reach with it’s current overclock in hertz.

### -field Voltage

[out] Voltage of the requested engine, represented in milli volts.

### -field VoltageMax

[out] The max voltage of the engine in milli volts while not overclocked.

### -field VoltageMaxOC

[out] The max voltage of the engine while overclocked in milli volts.

### -field MaxTransitionLatency

[out] The max transition latency to change the frequency, in 100 nanoseconds.
