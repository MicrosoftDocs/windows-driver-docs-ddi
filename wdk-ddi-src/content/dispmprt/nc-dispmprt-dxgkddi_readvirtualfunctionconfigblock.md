---
UID: NC:dispmprt.DXGKDDI_READVIRTUALFUNCTIONCONFIGBLOCK
title: DXGKDDI_READVIRTUALFUNCTIONCONFIGBLOCK
description: This routine supplies the non-privileged virtual machine (VM) with configuration data supplied by the Physical Function driver in the privileged VM.
tech.root: display
ms.assetid: d71bcf10-67b0-4300-bd52-d76cfcd865d1
ms.date: 04/04/2019
keywords: ["DXGKDDI_READVIRTUALFUNCTIONCONFIGBLOCK callback function"]
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
 - DXGKDDI_READVIRTUALFUNCTIONCONFIGBLOCK
 - dispmprt/DXGKDDI_READVIRTUALFUNCTIONCONFIGBLOCK
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - dispmprt.h
api_name:
 - DXGKDDI_READVIRTUALFUNCTIONCONFIGBLOCK
product:
 - Windows
dev_langs:
 - c++
---

# DXGKDDI_READVIRTUALFUNCTIONCONFIGBLOCK callback function


## -description

This routine supplies the non-privileged virtual machine (VM) with configuration data supplied by the Physical Function driver in the privileged VM. This is used by the virtual functions (VF) in order to read predefined configuration blocks from the PF. This function is only required if the guest VF driver expects it.

## -parameters

### -param Context

[in] The miniport context that is returned by the driver in the [DXGKDDI_SRIOV_INTERFACE](ns-dispmprt-_dxgkddi_sriov_interface.md) structure.

### -param pArgs

[in, out] A pointer to the DXGKARG_READVIRTUALFUNCTIONCONFIGBLOCK structure.

## -returns

Return STATUS_SUCCESS if the operation succeeds.

## -prototype

```
//Declaration

DXGKDDI_READVIRTUALFUNCTIONCONFIGBLOCK DxgkddiReadvirtualfunctionconfigblock; 

// Definition

NTSTATUS DxgkddiReadvirtualfunctionconfigblock 
(
	HANDLE Context
	DXGKARG_READVIRTUALFUNCTIONCONFIGBLOCK * pArgs
)
{...}

```

## -remarks

## -see-also

