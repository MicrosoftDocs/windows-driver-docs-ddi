---
UID: NC:dispmprt.DXGKDDI_SETTARGETADJUSTEDCOLORIMETRY2
title: DXGKDDI_SETTARGETADJUSTEDCOLORIMETRY2
author: windows-driver-content
description: Reports the colorimetry values selected by the OS for a target.
ms.assetid: 6177791c-0854-4902-bcbb-d5a58676dbb4
ms.date: 10/19/2018
ms.topic: callback
req.header: dispmprt.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
-	apiref
api_type: 
-	UserDefined
api_location: 
-	dispmprt.h
api_name: 
-	DXGKDDI_SETTARGETADJUSTEDCOLORIMETRY2
product:
-	Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# DXGKDDI_SETTARGETADJUSTEDCOLORIMETRY2 callback function

## -description

Reports the colorimetry values selected by the OS for a target.

## -prototype

```cpp
//Declaration

DXGKDDI_SETTARGETADJUSTEDCOLORIMETRY2 DxgkddiSettargetadjustedcolorimetry2; 

// Definition

NTSTATUS DxgkddiSettargetadjustedcolorimetry2 
(
	IN_CONST_HANDLE hAdapter
	IN_PDXGKARG_SETTARGETADJUSTEDCOLORIMETRY2 pArgSetTargetAdjustedColorimetry
)
{...}

```

## -parameters

### -param hAdapter

A handle to an adapter.

### -param pArgSetTargetAdjustedColorimetry: 

Pointer to a [DXGKARG_SETTARGETADJUSTEDCOLORIMETRY2](ns-dispmprt-_dxgkarg_settargetadjustedcolorimetry2.md) structure containing the colorimetry related fields for the monitor attached to this target after the OS has processed the display device descriptor, all overrides and any adjustments.

## -returns

The driver returns STATUS_SUCCESS if it has updates its colorimetry values based on the supplied data.

## -remarks



## -see-also
