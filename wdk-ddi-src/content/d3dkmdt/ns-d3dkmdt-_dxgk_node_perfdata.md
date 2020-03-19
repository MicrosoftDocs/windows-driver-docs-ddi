---
UID: NS:d3dkmdt._DXGK_NODE_PERFDATA
title: _DXGK_NODE_PERFDATA (d3dkmdt.h)
description: Input arguments for the call to node performance data.
ms.assetid: 3dd040ac-12ce-4fa6-81c5-b867dbe942ce
ms.date: 10/19/2018
keywords: ["_DXGK_NODE_PERFDATA structure"]
f1_keywords:
 - "d3dkmdt/_DXGK_NODE_PERFDATA"
ms.keywords: _DXGK_NODE_PERFDATA, DXGK_NODE_PERFDATA,
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
req.typenames: DXGK_NODE_PERFDATA
topic_type:
- apiref
api_type:
- HeaderDef
api_location:
- d3dkmdt.h
api_name:
- _DXGK_NODE_PERFDATA
product: 
- Windows
targetos: Windows
tech.root: display
---

# _DXGK_NODE_PERFDATA structure

## -description

Input arguments for the call to node performance data.

## -struct-fields

### -field Frequency

Clock frequency of the requested engine, represented in hertz.

### -field MaxFrequency

The max frequency the engine can normally reach in hertz while not overclocked.

### -field MaxFrequencyOC

The max frequency the engine can reach with it’s current overclock in hertz.

### -field Voltage

Voltage of the requested engine, represented in milli-volts.

### -field VoltageMax

The maximum voltage of the engine in milli-volts while not overclocked.

### -field VoltageMaxOC

The max voltage of the engine while overclocked in milli-volts.

### -field MaxTransitionLatency

The max transition latency.
