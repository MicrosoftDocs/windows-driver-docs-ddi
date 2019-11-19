---
UID: NC:dispmprt.DXGKDDI_QUERYPROBEDBARS
title: DXGKDDI_QUERYPROBEDBARS
author: windows-driver-content
description: 
tech.root: display
ms.assetid: 939bdb9f-a18f-4d49-8cbc-9b1c487e45c1
ms.author: windowsdriverdev
ms.date: 04/04/2019
ms.topic: callback
f1_keywords:
 - "dispmprt/DXGKDDI_QUERYPROBEDBARS"
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
 - DXGKDDI_QUERYPROBEDBARS
product: 
 - Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: 19H1
---

# DXGKDDI_QUERYPROBEDBARS callback function

## -description

This routine allows a non-privileged virtual machine to find out what would have been read from a Virtual Function’s Base Address Registers after they had been written with the value (-1). 

## -prototype

```
//Declaration

DXGKDDI_QUERYPROBEDBARS DxgkddiQueryprobedbars; 

// Definition

VOID DxgkddiQueryprobedbars 
(
	HANDLE Context
	DXGKARG_QUERYPROBEDBARS * pArgs
)
{...}

```

## -parameters

### -param Context

[in] The miniport context that is returned by the driver in the [DXGKDDI_SRIOV_INTERFACE](ns-dispmprt-_dxgkddi_sriov_interface.md) structure.

### -param pArgs

[in, out] Pointer to the DXGKARG_QUERYPROBEDBARS structure.

## -remarks

This is part of the normal process of setting up a PCI device, and the result allows the PCI driver to know how much address space would be decoded by the device after it was enabled. Because writing -1 to the physical BARS could be considered a security risk, this step of PCI enumeration is emulated.

## -see-also
