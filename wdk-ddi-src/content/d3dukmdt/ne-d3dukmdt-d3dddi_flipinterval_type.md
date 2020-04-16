---
UID: NE:d3dukmdt.D3DDDI_FLIPINTERVAL_TYPE
title: D3DDDI_FLIPINTERVAL_TYPE (d3dukmdt.h)
description: The D3DDDI_FLIPINTERVAL_TYPE enumeration type contains values that identify the type of flip that occurs in present operations.
old-location: display\d3dddi_flipinterval_type.htm
tech.root: display
ms.assetid: fbfc270c-b8e3-4467-b99d-2d5932a50114
ms.date: 05/10/2018
keywords: ["D3DDDI_FLIPINTERVAL_TYPE enumeration"]
ms.keywords: D3DDDI_FLIPINTERVAL_FOUR, D3DDDI_FLIPINTERVAL_IMMEDIATE, D3DDDI_FLIPINTERVAL_ONE, D3DDDI_FLIPINTERVAL_THREE, D3DDDI_FLIPINTERVAL_TWO, D3DDDI_FLIPINTERVAL_TYPE, D3DDDI_FLIPINTERVAL_TYPE enumeration [Display Devices], D3D_other_Structs_389c16ef-e25c-498e-994f-324efb96052c.xml, d3dukmdt/D3DDDI_FLIPINTERVAL_FOUR, d3dukmdt/D3DDDI_FLIPINTERVAL_IMMEDIATE, d3dukmdt/D3DDDI_FLIPINTERVAL_ONE, d3dukmdt/D3DDDI_FLIPINTERVAL_THREE, d3dukmdt/D3DDDI_FLIPINTERVAL_TWO, d3dukmdt/D3DDDI_FLIPINTERVAL_TYPE, display.d3dddi_flipinterval_type
f1_keywords:
 - "d3dukmdt/D3DDDI_FLIPINTERVAL_TYPE"
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dukmdt.h
api_name:
- D3DDDI_FLIPINTERVAL_TYPE
product:
- Windows
targetos: Windows
req.typenames: D3DDDI_FLIPINTERVAL_TYPE
---

# D3DDDI_FLIPINTERVAL_TYPE enumeration


## -description


The D3DDDI_FLIPINTERVAL_TYPE enumeration type contains values that identify the type of flip that occurs in present operations.


## -enum-fields




### -field D3DDDI_FLIPINTERVAL_IMMEDIATE

Indicates to perform the flip immediately without waiting for a vertical sync to occur. 


### -field D3DDDI_FLIPINTERVAL_ONE

Indicates to perform the flip on every vertical sync. 


### -field D3DDDI_FLIPINTERVAL_TWO

Indicates to perform the flip on every other vertical sync. 


### -field D3DDDI_FLIPINTERVAL_THREE

Indicates to perform the flip on every third vertical sync.


### -field D3DDDI_FLIPINTERVAL_FOUR

Indicates to perform the flip on every fourth vertical sync.


### -field D3DDDI_FLIPINTERVAL_IMMEDIATE_ALLOW_TEARING




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_present">DXGKARG_PRESENT</a>
 

 

