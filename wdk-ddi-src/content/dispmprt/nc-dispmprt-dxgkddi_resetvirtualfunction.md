---
UID: NC:dispmprt.DXGKDDI_RESETVIRTUALFUNCTION
title: DXGKDDI_RESETVIRTUALFUNCTION
description: This routine allows the virtualized I/O management software running in the privileged virtual machine to reset a specific virtual function.
tech.root: display
ms.assetid: bb0b629c-fa1a-444e-8f28-80df998668b2
ms.date: 04/04/2019
keywords: ["DXGKDDI_RESETVIRTUALFUNCTION callback function"]
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
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - DXGKDDI_RESETVIRTUALFUNCTION
 - dispmprt/DXGKDDI_RESETVIRTUALFUNCTION
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - dispmprt.h
api_name:
 - DXGKDDI_RESETVIRTUALFUNCTION
product:
 - Windows
dev_langs:
 - c++
---

# DXGKDDI_RESETVIRTUALFUNCTION callback function


## -description

This routine allows the virtualized I/O management software running in the privileged virtual machine to reset a specific virtual function.

## -parameters

### -param Context

[in] The miniport context that is returned by the driver in the [DXGKDDI_SRIOV_INTERFACE](ns-dispmprt-_dxgkddi_sriov_interface.md) structure.

### -param pArgs

[in, out] A pointer to a DXGKARG_RESETVIRTUALFUNCTION structure.

## -returns

Return STATUS_SUCCESS if the operation succeeds.

## -prototype

```
//Declaration

DXGKDDI_RESETVIRTUALFUNCTION DxgkddiResetvirtualfunction; 

// Definition

NTSTATUS DxgkddiResetvirtualfunction 
(
	HANDLE Context
	DXGKARG_RESETVIRTUALFUNCTION * pArgs
)
{...}

```

## -remarks

## -see-also

