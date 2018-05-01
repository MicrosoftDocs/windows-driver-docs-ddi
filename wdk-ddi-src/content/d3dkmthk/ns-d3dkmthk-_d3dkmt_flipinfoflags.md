---
UID: NS:d3dkmthk._D3DKMT_FLIPINFOFLAGS
title: "_D3DKMT_FLIPINFOFLAGS"
author: windows-driver-content
description: The D3DKMT_FLIPINFOFLAGS structure identifies flipping capabilities of the display miniport driver that the OpenGL installable client driver (ICD) obtains by calling the D3DKMTQueryAdapterInfo function.
old-location: display\d3dkmt_flipinfoflags.htm
old-project: display
ms.assetid: 61b6d477-5a4c-475c-8605-5ede592e75c1
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3DKMT_FLIPINFOFLAGS, D3DKMT_FLIPINFOFLAGS structure [Display Devices], OpenGL_Structs_2e8d2e1b-7ae8-4ac4-916d-5cace7ef043e.xml, _D3DKMT_FLIPINFOFLAGS, d3dkmthk/D3DKMT_FLIPINFOFLAGS, display.d3dkmt_flipinfoflags
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
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
-	d3dkmthk.h
api_name:
-	D3DKMT_FLIPINFOFLAGS
product: Windows
targetos: Windows
req.typenames: D3DKMT_FLIPINFOFLAGS
---

# _D3DKMT_FLIPINFOFLAGS structure


## -description


The D3DKMT_FLIPINFOFLAGS structure identifies flipping capabilities of the display miniport driver that the OpenGL installable client driver (ICD) obtains by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547100">D3DKMTQueryAdapterInfo</a> function.


## -struct-fields




### -field FlipInterval

A UINT value that specifies whether the display miniport driver natively supports the scheduling of a flip command to take effect after two, three or four vertical syncs occur. Regardless of whether the display miniport driver supports a flip interval of two or greater, the driver must support an immediate flip and a flip interval of one.

Setting this member is equivalent to setting the first bit of a 32-bit value (0x00000001).


### -field Reserved

This member is reserved and should be set to zero. Setting this member is equivalent to setting the remaining 31 bits (0xFFFFFFFE) of a 32-bit value to zeros. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547100">D3DKMTQueryAdapterInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548010">D3DKMT_FLIPQUEUEINFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548203">D3DKMT_QUERYADAPTERINFO</a>
 

 

