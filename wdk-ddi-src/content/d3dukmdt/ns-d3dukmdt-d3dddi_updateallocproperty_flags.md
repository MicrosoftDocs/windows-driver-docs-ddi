---
UID: NS:d3dukmdt.D3DDDI_UPDATEALLOCPROPERTY_FLAGS
title: D3DDDI_UPDATEALLOCPROPERTY_FLAGS (d3dukmdt.h)
description: The D3DDDI_UPDATEALLOCPROPERTY_FLAGS structure identifies how to update a property in an allocation.
old-location: display\d3dddi_updateallocproperty_flags.htm
tech.root: display
ms.assetid: 377EC824-9D43-40CA-B5CA-A04402852EA3
ms.date: 05/10/2018
keywords: ["D3DDDI_UPDATEALLOCPROPERTY_FLAGS structure"]
ms.keywords: D3DDDI_UPDATEALLOCPROPERTY_FLAGS, D3DDDI_UPDATEALLOCPROPERTY_FLAGS structure [Display Devices], PD3DDDI_UPDATEALLOCPROPERTY_FLAGS, PD3DDDI_UPDATEALLOCPROPERTY_FLAGS structure pointer [Display Devices], d3dukmdt/D3DDDI_UPDATEALLOCPROPERTY_FLAGS, d3dukmdt/PD3DDDI_UPDATEALLOCPROPERTY_FLAGS, display.d3dddi_updateallocproperty_flags
req.header: d3dukmdt.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: D3DDDI_UPDATEALLOCPROPERTY_FLAGS
f1_keywords:
 - D3DDDI_UPDATEALLOCPROPERTY_FLAGS
 - d3dukmdt/D3DDDI_UPDATEALLOCPROPERTY_FLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dukmdt.h
api_name:
 - D3DDDI_UPDATEALLOCPROPERTY_FLAGS
---

# D3DDDI_UPDATEALLOCPROPERTY_FLAGS structure


## -description

The D3DDDI_UPDATEALLOCPROPERTY_FLAGS structure identifies how to update a property in an allocation.

## -struct-fields

### -field AccessedPhysically

A UINT value that specifies whether the allocation is accessed by its physical address.

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).

### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 31 bits (0xFFFFFFFE) of the 32-bit <b>Value</b> member to zeros.

### -field Value

A member in the union that is contained in D3DDDI_UPDATEALLOC_PROPERTY_FLAGS that can hold one 32-bit value that identifies how to unlock a resource.

