---
UID: NS:d3dkmddi._DXGK_MAPAPERTUREFLAGS
title: "_DXGK_MAPAPERTUREFLAGS"
author: windows-driver-content
description: The DXGK_MAPAPERTUREFLAGS structure identifies the type of map-aperture-segment operation to set up in a call to the DxgkDdiBuildPagingBuffer function.
old-location: display\dxgk_mapapertureflags.htm
old-project: display
ms.assetid: c6a6f98f-a4e3-47ed-b9e9-7303c824612d
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGK_MAPAPERTUREFLAGS structure [Display Devices], DmStructs_74b5ec6e-0c62-419f-beb2-676d993c7496.xml, DXGK_MAPAPERTUREFLAGS, _DXGK_MAPAPERTUREFLAGS, display.dxgk_mapapertureflags, d3dkmddi/DXGK_MAPAPERTUREFLAGS
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGK_MAPAPERTUREFLAGS
product: Windows
targetos: Windows
req.typenames: DXGK_MAPAPERTUREFLAGS
---

# _DXGK_MAPAPERTUREFLAGS structure


## -description


The DXGK_MAPAPERTUREFLAGS structure identifies the type of map-aperture-segment operation to set up in a call to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_buildpagingbuffer.md">DxgkDdiBuildPagingBuffer</a> function. 


## -syntax


````
typedef struct _DXGK_MAPAPERTUREFLAGS {
  union {
    struct {
      UINT CacheCoherent  :1;
      UINT Reserved  :31;
    };
    UINT Value;
  };
} DXGK_MAPAPERTUREFLAGS;
````


## -struct-fields




### -field CacheCoherent

[in] A UINT value that specifies whether cache coherency is required for pages that are mapped in a call to <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_buildpagingbuffer.md">DxgkDdiBuildPagingBuffer</a>. If this member is set, the driver must ensure that cache coherency is enforced on the pages that are mapped. If this member is not set, cache coherency is not required for the pages that are mapped. 

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field Reserved

[in] This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 31 bits (0xFFFFFFFE) of the 32-bit <b>Value</b> member to zeros.


### -field Value

[in] A member in the union that DXGK_MAPAPERTUREFLAGS contains that can hold a 32-bit value that identifies the type of map-aperture-segment-operation.


## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_buildpagingbuffer.md">DxgkDdiBuildPagingBuffer</a>

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_buildpagingbuffer.md">DXGKARG_BUILDPAGINGBUFFER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_MAPAPERTUREFLAGS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

