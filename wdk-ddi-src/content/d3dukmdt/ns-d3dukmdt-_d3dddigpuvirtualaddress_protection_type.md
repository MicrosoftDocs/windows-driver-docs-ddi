---
UID: NS:d3dukmdt._D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE
title: D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE (d3dukmdt.h)
description: Learn more about the D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE structure.
tech.root: display
ms.date: 07/25/2023
keywords: ["D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE structure"]
ms.keywords: D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE, D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE structure [Display Devices], _D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE, d3dukmdt/D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE, display.d3dddigpuvirtualaddress_protection_type
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.typenames: D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE
f1_keywords:
 - _D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE
 - d3dukmdt/_D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE
 - D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE
 - d3dukmdt/D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dukmdt.h
api_name:
 - _D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE
 - D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE
---

# D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE structure

## -description

The **D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE** structure specifies the protection on the GPU virtual address that is mapped.

## -struct-fields

### -field Write

The pages will be allowed read-write access.

### -field Execute

The pages will be allowed execute access.

### -field Zero

The pages will be put to the *Zero* state ([**hAllocation**](ns-d3dukmdt-d3dddi_mapgpuvirtualaddress.md) must be NULL). Reads return zero and writes are discarded in this state.

### -field NoAccess

The pages will be put to the *Invalid* state ([**hAllocation**](ns-d3dukmdt-d3dddi_mapgpuvirtualaddress.md) must be NULL).

### -field SystemUseOnly

This member is for system use only and should not be set by the user-mode driver.

### -field Reserved

This member is reserved and should be set to zero.

### -field Value

The consolidated value of the structure's members.

## -see-also

[**D3DDDI_MAPGPUVIRTUALADDRESS**](ns-d3dukmdt-d3dddi_mapgpuvirtualaddress.md)
