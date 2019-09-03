---
UID: NC:dispmprt.DXGKDDI_RESETVIRTUALFUNCTION
title: DXGKDDI_RESETVIRTUALFUNCTION
author: windows-driver-content
description: This routine allows the virtualized I/O management software running in the privileged virtual machine to reset a specific virtual function.
tech.root: display
ms.assetid: bb0b629c-fa1a-444e-8f28-80df998668b2
ms.author: windowsdriverdev
ms.date: 04/04/2019
ms.topic: callback
f1_keywords:
 - "dispmprt/DXGKDDI_RESETVIRTUALFUNCTION"
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
 - apiref
api_type: 
 - UserDefined
api_location: 
 - dispmprt.h
api_name: 
 - DXGKDDI_RESETVIRTUALFUNCTION
product: 
 - Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: 19H1
---

# DXGKDDI_RESETVIRTUALFUNCTION callback function

## -description

This routine allows the virtualized I/O management software running in the privileged virtual machine to reset a specific virtual function.

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

## -parameters

### -param Context

[in] The miniport context that is returned by the driver in the [DXGKDDI_SRIOV_INTERFACE](ns-dispmprt-_dxgkddi_sriov_interface.md) structure.

### -param pArgs

[in, out] A pointer to a DXGKARG_RESETVIRTUALFUNCTION structure.

## -returns

Return STATUS_SUCCESS if the operation succeeds.

## -remarks




## -see-also
