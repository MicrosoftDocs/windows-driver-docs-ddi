---
UID: NC:dispmprt.DXGKDDI_GETDEVICELOCATION
title: DXGKDDI_GETDEVICELOCATION
author: windows-driver-content
description: Returns the location of a Virtual Function on the PCI bus relative to the root partition.
tech.root: display
ms.assetid: 9940a83c-dc9c-4ac0-94d3-52728a76f870
ms.author: windowsdriverdev
ms.date: 04/04/2019
ms.topic: callback
req.header: dispmprt.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: PASSIVE_LEVEL
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
 - DXGKDDI_GETDEVICELOCATION
product: 
 - Windows
targetos: Windows
---

# DXGKDDI_GETDEVICELOCATION callback function

## -description

Returns the location of a Virtual Function on the PCI bus relative to the root partition. If an IHV implementation does not support SR-IOV, the location of the physical function is returned.

## -prototype

```
//Declaration

DXGKDDI_GETDEVICELOCATION DxgkddiGetdevicelocation; 

// Definition

VOID DxgkddiGetdevicelocation 
(
	HANDLE Context
	DXGKARG_GETDEVICELOCATION * pArgs
)
{...}

```

## -parameters

### -param Context

The miniport context that is returned by the driver in the [DXGKDDI_SRIOV_INTERFACE](ns-dispmprt-_dxgkddi_sriov_interface.md) structure.

### -param pArgs

Pointer to the DXGKARG_GETDEVICELOCATION structure.

## -returns

Returns VOID.

## -remarks

VF indices are incrementing, but the bus location is not directly tied to the index. This function retrieves the actual PCIe bus location of a virtual function.


## -see-also