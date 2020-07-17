---
UID: NC:dispmprt.DXGKDDI_WRITEVIRTUALFUNCTIONCONFIGBLOCK
title: DXGKDDI_WRITEVIRTUALFUNCTIONCONFIGBLOCK
author: windows-driver-content
description: This function allows the non-privileged virtual machine to write configuration data supplied by the Physical Function driver in the privileged VM.
tech.root: display
ms.assetid: faac7ab9-5120-4f67-a968-96582f0f980d
ms.author: windowsdriverdev
ms.date: 04/04/2019
keywords: ["DXGKDDI_WRITEVIRTUALFUNCTIONCONFIGBLOCK callback function"]
f1_keywords:
 - "dispmprt/DXGKDDI_WRITEVIRTUALFUNCTIONCONFIGBLOCK"
 - "DXGKDDI_WRITEVIRTUALFUNCTIONCONFIGBLOCK"
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
 - DXGKDDI_WRITEVIRTUALFUNCTIONCONFIGBLOCK
product: 
 - Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: 19H1
---

# DXGKDDI_WRITEVIRTUALFUNCTIONCONFIGBLOCK callback function

## -description

This function allows the non-privileged virtual machine to write configuration data supplied by the Physical Function driver in the privileged VM. This is used by the VFs in order to write configuration block data to the PF.  This function is only required if the guest VF driver expects it.

## -prototype

```
//Declaration

DXGKDDI_WRITEVIRTUALFUNCTIONCONFIGBLOCK DxgkddiWritevirtualfunctionconfigblock; 

// Definition

NTSTATUS DxgkddiWritevirtualfunctionconfigblock 
(
	HANDLE Context
	DXGKARG_WRITEVIRTUALFUNCTIONCONFIGBLOCK * pArgs
)
{...}

```

## -parameters

### -param Context

[in] The miniport context that is returned by the driver in the [DXGKDDI_SRIOV_INTERFACE](ns-dispmprt-_dxgkddi_sriov_interface.md) structure.

### -param pArgs

[in] A pointer to a DXGKARG_WRITEVIRTUALFUNCTIONCONFIGBLOCK structure.

## -returns

Return STATUS_SUCCESS if the operation succeeds.

## -remarks




## -see-also
