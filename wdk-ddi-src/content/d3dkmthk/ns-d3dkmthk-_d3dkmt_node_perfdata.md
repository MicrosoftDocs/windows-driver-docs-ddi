---
UID: NS:d3dkmthk._D3DKMT_NODE_PERFDATA
title: _D3DKMT_NODE_PERFDATA
author: windows-driver-content
description: Represents performance data collected per engine from an adapter on an interval basis.
ms.assetid: 90d91283-4891-4459-b182-40bf600c8b92
ms.author: windowsdriverdev
ms.date:
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	apiref
api_type:
-	HeaderDef
api_location:
-	d3dkmthk.h
api_name:
-	_D3DKMT_NODE_PERFDATA
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

Node ordinal of the requested engine.

### -field PhysicalAdapterIndex

The physical adapter index in a LDA chain.

### -field Frequency

Clock frequency of the requested engine, represented in hertz.

### -field MaxFrequency

The max frequency the engine can normally reach in hertz while not overclocked.

### -field MaxFrequencyOC

The max frequency the engine can reach with it’s current overclock in hertz.

### -field Voltage

Voltage of the requested engine, represented in milli volts.

### -field VoltageMax

The max voltage of the engine in milli volts while not overclocked.

### -field VoltageMaxOC

The max voltage of the engine while overclocked in milli volts.

