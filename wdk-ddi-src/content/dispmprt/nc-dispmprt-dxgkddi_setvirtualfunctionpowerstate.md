---
UID: NC:dispmprt.DXGKDDI_SETVIRTUALFUNCTIONPOWERSTATE
title: DXGKDDI_SETVIRTUALFUNCTIONPOWERSTATE
description: This routine allows a non-privileged virtual machine to change the power state of a PCI Express SR-IOV Virtual Function.
tech.root: display
ms.assetid: 6bba2af7-723d-4dfa-8efc-ec57e991a837
ms.date: 04/04/2019
keywords: ["DXGKDDI_SETVIRTUALFUNCTIONPOWERSTATE callback function"]
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
 - DXGKDDI_SETVIRTUALFUNCTIONPOWERSTATE
 - dispmprt/DXGKDDI_SETVIRTUALFUNCTIONPOWERSTATE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - dispmprt.h
api_name:
 - DXGKDDI_SETVIRTUALFUNCTIONPOWERSTATE
product:
 - Windows
dev_langs:
 - c++
---

# DXGKDDI_SETVIRTUALFUNCTIONPOWERSTATE callback function


## -description

This routine allows a non-privileged virtual machine to change the power state of a PCI Express SR-IOV Virtual Function.

## -parameters

### -param Context

[in] The miniport context that is returned by the driver in the [DXGKDDI_SRIOV_INTERFACE](ns-dispmprt-_dxgkddi_sriov_interface.md) structure.

### -param pArgs

[in] A pointer to a DXGKARG_SETVIRTUALFUNCTIONPOWERSTATE structure.

## -returns

Return STATUS_SUCCESS if the operation succeeds.

## -prototype

```
//Declaration

DXGKDDI_SETVIRTUALFUNCTIONPOWERSTATE DxgkddiSetvirtualfunctionpowerstate; 

// Definition

NTSTATUS DxgkddiSetvirtualfunctionpowerstate 
(
	HANDLE Context
	DXGKARG_SETVIRTUALFUNCTIONPOWERSTATE * pArgs
)
{...}

```

## -remarks

When all vGPUs are in a D3 state and if the Host doesn’t need the GPU, the physical GPU will be put into a D3 Cold state in which case the PF and all of the VF will become inaccessible until the GPU is powered up again. Upon power up we expect the same PF/VF configuration to be in effect as before the power down.

## -see-also

