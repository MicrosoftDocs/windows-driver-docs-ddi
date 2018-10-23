---
UID: NS:d3dumddi._D3DDDI_UNLOCKFLAGS
title: "_D3DDDI_UNLOCKFLAGS"
author: windows-driver-content
description: The D3DDDI_UNLOCKFLAGS structure identifies how to unlock a resource.
old-location: display\d3dddi_unlockflags.htm
tech.root: display
ms.assetid: f3c3356c-ec7b-4869-896d-9d3b285f0e87
ms.date: 05/10/2018
ms.keywords: D3DDDI_UNLOCKFLAGS, D3DDDI_UNLOCKFLAGS structure [Display Devices], D3D_other_Structs_c1133d3b-9330-4278-85c7-4083436278cf.xml, _D3DDDI_UNLOCKFLAGS, d3dumddi/D3DDDI_UNLOCKFLAGS, display.d3dddi_unlockflags
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	D3DDDI_UNLOCKFLAGS
product:
- Windows
targetos: Windows
req.typenames: D3DDDI_UNLOCKFLAGS
---

# _D3DDDI_UNLOCKFLAGS structure


## -description


The D3DDDI_UNLOCKFLAGS structure identifies how to unlock a resource.


## -struct-fields




### -field NotifyOnly

A UINT value that specifies whether the unlock call is for notification only.

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 31 bits (0xFFFFFFFE) of the 32-bit <b>Value</b> member to zeros.


### -field Value

A member in the union that is contained in D3DDDI_UNLOCKFLAGS that can hold one 32-bit value that identifies how to unlock a resource.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543394">D3DDDIARG_UNLOCK</a>
 

 

