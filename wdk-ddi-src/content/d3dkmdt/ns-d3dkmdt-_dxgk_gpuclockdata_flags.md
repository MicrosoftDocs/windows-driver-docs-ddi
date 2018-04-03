---
UID: NS:d3dkmdt._DXGK_GPUCLOCKDATA_FLAGS
title: _DXGK_GPUCLOCKDATA_FLAGS
author: windows-driver-content
description:
ms.assetid: 24796b6b-4381-48a7-93af-e8e5273bd07a
ms.author: windowsdriverdev
ms.date:
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _DXGK_GPUCLOCKDATA_FLAGS, DXGK_GPUCLOCKDATA_FLAGS,
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
req.typenames: DXGK_GPUCLOCKDATA_FLAGS
topictype:
-	apiref
apitype:
-	HeaderDef
apilocation:
-	d3dkmdt.h
apiname:
-	_DXGK_GPUCLOCKDATA_FLAGS
product: Windows
targetos: Windows
---

# _DXGK_GPUCLOCKDATA_FLAGS structure

## -description

> [!Warning]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.

Contains information about the GPU clock data flags.

## -struct-fields

### -field ContextManagementProcessor

A context management processor flag.

### -field Reserved

Reserved.

### -field Value

value of the GPU clock data.

## -remarks

As long as the GPU is powered on:

* The context management processor for a GPU node is expected to have access to a clock that is always counting.
* The clock frequency on the context management processor is expected to remain constant.

When a GPU node is initialized, the OS calibrates the GPU clock against the CPU clock using [DxgkDdiCalibrateGpuClock](..\d3dkmddi\nc-d3dkmddi-dxgkddi_calibrategpuclock.md) function with the ContextManagementProcessor flag. The flag differentiates between using DdiCalibrateGpuClock() to obtain the underlying GPU engine clock, or to obtain the context management processor clock, that may be different from the GPU engine clock.

## -see-also

[DxgkDdiCalibrateGpuClock](..\d3dkmddi\nc-d3dkmddi-dxgkddi_calibrategpuclock.md)