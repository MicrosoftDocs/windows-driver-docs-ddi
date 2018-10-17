---
UID: NC:d3dkmddi.DXGKDDI_SETTRACKEDWORKLOADPOWERLEVEL
title: DXGKDDI_SETTRACKEDWORKLOADPOWERLEVEL
author: windows-driver-content
description: Called by the workload tracker to modify the power level on a context.
ms.assetid: 57ba5418-457e-4859-adf7-1c3d842de2bc
ms.date: 
ms.topic: callback
req.header: d3dkmddi.h
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
-	d3dkmddi.h
api_name: 
-	DXGKDDI_SETTRACKEDWORKLOADPOWERLEVEL
product:
-	Windows
targetos: Windows
tech.root: display
---

# DXGKDDI_SETTRACKEDWORKLOADPOWERLEVEL callback function

## -description

Called by the workload tracker to modify the power level on a context.

## -prototype

```
//Declaration

DXGKDDI_SETTRACKEDWORKLOADPOWERLEVEL DxgkddiSettrackedworkloadpowerlevel; 

// Definition

NTSTATUS DxgkddiSettrackedworkloadpowerlevel 
(
	IN_CONST_HANDLE hContext
	INOUT_PDXGKARG_SETTRACKEDWORKLOADPOWERLEVEL pTrackedWorkloadPowerLevel
)
{...}

```

## -parameters

### -param hContext

A handle to the hardware context.

### -param pTrackedWorkloadPowerLevel

Pointer to a [DXGKARG_SETTRACKEDWORKLOADPOWERLEVEL](ns-d3dkmddi-_dxgkarg_settrackedworkloadpowerlevel.md) structure.



## -returns

Returns NTSTATUS.


## -remarks

If the next packet submission for this context takes place, then the new frequency/configuration parameters for the GPU should be effective. The OS will just call the DDI to set the ratio if it changes significantly from the previously computed level. Whenever we switch to this context, the driver needs to make sure the correct GPU configuration including the appropriate frequencies is applied to any subsequent packets execution.


## -see-also
