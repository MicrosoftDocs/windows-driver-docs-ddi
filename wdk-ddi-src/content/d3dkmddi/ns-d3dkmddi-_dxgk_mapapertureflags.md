---
UID: NS:d3dkmddi._DXGK_MAPAPERTUREFLAGS
title: "_DXGK_MAPAPERTUREFLAGS"
author: windows-driver-content
description: The DXGK_MAPAPERTUREFLAGS structure identifies the type of map-aperture-segment operation to set up in a call to the DxgkDdiBuildPagingBuffer function.
old-location: display\dxgk_mapapertureflags.htm
old-project: display
ms.assetid: c6a6f98f-a4e3-47ed-b9e9-7303c824612d
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: DXGK_MAPAPERTUREFLAGS, DXGK_MAPAPERTUREFLAGS structure [Display Devices], DmStructs_74b5ec6e-0c62-419f-beb2-676d993c7496.xml, _DXGK_MAPAPERTUREFLAGS, d3dkmddi/DXGK_MAPAPERTUREFLAGS, display.dxgk_mapapertureflags
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
-	d3dkmddi.h
api_name:
-	DXGK_MAPAPERTUREFLAGS
product: Windows
targetos: Windows
req.typenames: DXGK_MAPAPERTUREFLAGS
---

# _DXGK_MAPAPERTUREFLAGS structure


## -description


The DXGK_MAPAPERTUREFLAGS structure identifies the type of map-aperture-segment operation to set up in a call to the <a href="https://msdn.microsoft.com/d315ff53-4a9f-46a3-ad74-d65a5eb72de1">DxgkDdiBuildPagingBuffer</a> function. 


## -struct-fields




### -field CacheCoherent

[in] A UINT value that specifies whether cache coherency is required for pages that are mapped in a call to <a href="https://msdn.microsoft.com/d315ff53-4a9f-46a3-ad74-d65a5eb72de1">DxgkDdiBuildPagingBuffer</a>. If this member is set, the driver must ensure that cache coherency is enforced on the pages that are mapped. If this member is not set, cache coherency is not required for the pages that are mapped. 

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field Reserved

[in] This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 31 bits (0xFFFFFFFE) of the 32-bit <b>Value</b> member to zeros.


### -field Value

[in] A member in the union that DXGK_MAPAPERTUREFLAGS contains that can hold a 32-bit value that identifies the type of map-aperture-segment-operation.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557540">DXGKARG_BUILDPAGINGBUFFER</a>



<a href="https://msdn.microsoft.com/d315ff53-4a9f-46a3-ad74-d65a5eb72de1">DxgkDdiBuildPagingBuffer</a>
 

 

