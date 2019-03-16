---
UID: NS:d3dumddi.D3DDDIARG_COPYFLAGS
title: D3DDDIARG_COPYFLAGS (d3dumddi.h)
description: Describes how to handle the existing contents of a resource during a copy or update operation of a region within that resource. Used by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers.
old-location: display\d3dddiarg_copyflags.htm
tech.root: display
ms.assetid: DA114D60-60EE-4D1D-B42C-A84CE54C8B95
ms.date: 05/10/2018
ms.keywords: D3DDDIARG_COPYFLAGS, D3DDDIARG_COPYFLAGS structure [Display Devices], d3dumddi/D3DDDIARG_COPYFLAGS, display.d3dddiarg_copyflags
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
- D3dumddi.h
api_name:
- D3DDDIARG_COPYFLAGS
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_COPYFLAGS
---

# D3DDDIARG_COPYFLAGS structure


## -description


Describes how to handle the existing contents of a resource during a copy or update operation of a region within that resource. Used by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers.


## -struct-fields




### -field NoOverwrite

Specifies that the caller guarantees that the portion of the surface that is being written to with new data is not currently being referenced or accessed by any previous render operation. The driver can take advantage of this capability to optimize performance and memory usage.

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field Discard

Specifies that the user-mode display driver can discard previous contents of the entire resource. The driver can take advantage of this capability to optimize performance and memory usage.

Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).


### -field Reserved1

This member is reserved and should be set to zero.

Setting this member to zero is equivalent to setting bits 3 through 24 (0x00FFFFFC) of the 32-bit <b>Value</b> member to zeros.


### -field BoxValid

Specifies that a destination region of the subresource to be copied to is valid. When not set, the entire subresource must be updated.

Setting this member is equivalent to setting the twenty-fifth bit of the 32-bit <b>Value</b> member (0x01000000).


### -field Reserved2

This member is reserved and should be set to zero.

Setting this member to zero is equivalent to setting bits 26 through 32 (0xFE000000) of the 32-bit <b>Value</b> member to zeros.


### -field Value

A member in the union that <b>D3DDDIARG_COPYFLAGS</b> contains that can hold a 32-bit value that identifies how to handle the existing contents of a resource during a copy or update operation.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn449153">D3DDDIARG_UPDATESUBRESOURCEUP</a>
 

 

