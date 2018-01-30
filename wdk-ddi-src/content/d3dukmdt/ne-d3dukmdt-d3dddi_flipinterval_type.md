---
UID: NE:d3dukmdt.D3DDDI_FLIPINTERVAL_TYPE
title: D3DDDI_FLIPINTERVAL_TYPE
author: windows-driver-content
description: The D3DDDI_FLIPINTERVAL_TYPE enumeration type contains values that identify the type of flip that occurs in present operations.
old-location: display\d3dddi_flipinterval_type.htm
old-project: display
ms.assetid: fbfc270c-b8e3-4467-b99d-2d5932a50114
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DDDI_FLIPINTERVAL_IMMEDIATE, D3D_other_Structs_389c16ef-e25c-498e-994f-324efb96052c.xml, D3DDDI_FLIPINTERVAL_ONE, d3dukmdt/D3DDDI_FLIPINTERVAL_TYPE, d3dukmdt/D3DDDI_FLIPINTERVAL_THREE, display.d3dddi_flipinterval_type, d3dukmdt/D3DDDI_FLIPINTERVAL_IMMEDIATE, D3DDDI_FLIPINTERVAL_THREE, D3DDDI_FLIPINTERVAL_FOUR, d3dukmdt/D3DDDI_FLIPINTERVAL_TWO, d3dukmdt/D3DDDI_FLIPINTERVAL_FOUR, d3dukmdt/D3DDDI_FLIPINTERVAL_ONE, D3DDDI_FLIPINTERVAL_TWO, D3DDDI_FLIPINTERVAL_TYPE, D3DDDI_FLIPINTERVAL_TYPE enumeration [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dukmdt.h
apiname:
-	D3DDDI_FLIPINTERVAL_TYPE
product: Windows
targetos: Windows
req.typenames: D3DDDI_FLIPINTERVAL_TYPE
---

# D3DDDI_FLIPINTERVAL_TYPE enumeration


## -description


The D3DDDI_FLIPINTERVAL_TYPE enumeration type contains values that identify the type of flip that occurs in present operations.


## -syntax


````
typedef enum D3DDDI_FLIPINTERVAL_TYPE { 
  D3DDDI_FLIPINTERVAL_IMMEDIATE  = 0,
  D3DDDI_FLIPINTERVAL_ONE        = 1,
  D3DDDI_FLIPINTERVAL_TWO        = 2,
  D3DDDI_FLIPINTERVAL_THREE      = 3,
  D3DDDI_FLIPINTERVAL_FOUR       = 4
} D3DDDI_FLIPINTERVAL_TYPE;
````


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

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_present.md">DXGKARG_PRESENT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_FLIPINTERVAL_TYPE enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

