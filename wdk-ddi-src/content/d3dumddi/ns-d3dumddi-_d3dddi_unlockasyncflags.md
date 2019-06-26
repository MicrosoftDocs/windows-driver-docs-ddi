---
UID: NS:d3dumddi._D3DDDI_UNLOCKASYNCFLAGS
title: _D3DDDI_UNLOCKASYNCFLAGS (d3dumddi.h)
description: The D3DDDI_UNLOCKASYNCFLAGS structure identifies how to unlock a resource.
old-location: display\d3dddi_unlockasyncflags.htm
tech.root: display
ms.assetid: c31e4a4e-7bc7-43a2-8f86-e79012064fa2
ms.date: 05/10/2018
ms.keywords: D3DDDI_UNLOCKASYNCFLAGS, D3DDDI_UNLOCKASYNCFLAGS structure [Display Devices], D3D_other_Structs_d42c29f4-23e8-4b5c-8710-2e4153c857bf.xml, _D3DDDI_UNLOCKASYNCFLAGS, d3dumddi/D3DDDI_UNLOCKASYNCFLAGS, display.d3dddi_unlockasyncflags
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
- d3dumddi.h
api_name:
- D3DDDI_UNLOCKASYNCFLAGS
product:
- Windows
targetos: Windows
req.typenames: D3DDDI_UNLOCKASYNCFLAGS
---

# _D3DDDI_UNLOCKASYNCFLAGS structure


## -description


The D3DDDI_UNLOCKASYNCFLAGS structure identifies how to unlock a resource.


## -struct-fields




### -field NotifyOnly

A UINT value that specifies whether the unlock call is for notification only. The Microsoft Direct3D runtime sets <b>NotifyOnly</b> to <b>TRUE</b> when it unlocks runtime-allocated system memory surfaces. 

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 31 bits (0xFFFFFFFE) of the 32-bit <b>Value</b> member to zeros.


### -field Value

A member in the union that is contained in D3DDDI_UNLOCKASYNCFLAGS that can hold one 32-bit value that identifies how to unlock a resource.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddiarg_unlock">D3DDDIARG_UNLOCK</a>
 

 

