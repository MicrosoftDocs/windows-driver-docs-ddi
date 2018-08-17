---
UID: NS:d3dkmdt._DXGK_ADAPTER_PERFDATA
title: _DXGK_ADAPTER_PERFDATA
author: windows-driver-content
description:
ms.assetid: 2c419e37-47ba-4b85-9994-2b3a5769c903
ms.author: windowsdriverdev
ms.date:
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _DXGK_ADAPTER_PERFDATA, DXGK_ADAPTER_PERFDATA,
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
req.typenames: DXGK_ADAPTER_PERFDATA
topic_type:
-	apiref
api_type:
-	HeaderDef
api_location:
-	d3dkmdt.h
api_name:
-	_DXGK_ADAPTER_PERFDATA
product: 
- Windows
targetos: Windows
tech.root: display
---

# _DXGK_ADAPTER_PERFDATA structure

## -description

Contains the display adapter performance data.

## -struct-fields

### -field MemoryFrequency

Clock frequency of the requested engine, represented in hertz.

### -field MaxMemoryFrequency

Max clock frequency of the memory while not overclocked, represented in hertz.

### -field MaxMemoryFrequencyOC

The max frequency the engine can reach with it’s current overclock in hertz.

### -field MemoryBandwidth

Amount of total memory transferred in bytes.

### -field PCIEBandwidth

Amount of total memory transferred over the PCIE in bytes.

### -field FanRPM

The current rpm of the main fan.

### -field Power

The current power draw of the adapter in tenths of percentage, 1 = 0.1%.

### -field Temperature

The main temperature sensors reading in decimal Celsius. 1 = 0.1C.

### -field PowerStateOverride

Reports if the GPU is powered on with 1 otherwise it is 0. This overrides dxgkrnl’s adapter level view for a better understanding of each physical GPU that are linked together.

