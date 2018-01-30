---
UID: NS:dxgiddi.DXGI_DDI_PRESENT_FLAGS
title: DXGI_DDI_PRESENT_FLAGS
author: windows-driver-content
description: Identifies how to perform a present operation.
old-location: display\dxgi_ddi_present_flags.htm
old-project: display
ms.assetid: 87f3b66a-0fcb-4325-ae23-7f89d6b389e6
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGI_DDI_PRESENT_FLAGS structure [Display Devices], UMDisplayDriver_Dx10param_Structs_75234d4d-acce-4f1f-804c-f7128d885c2f.xml, display.dxgi_ddi_present_flags, dxgiddi/DXGI_DDI_PRESENT_FLAGS, DXGI_DDI_PRESENT_FLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
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
-	dxgiddi.h
apiname:
-	DXGI_DDI_PRESENT_FLAGS
product: Windows
targetos: Windows
req.typenames: DXGI_DDI_PRESENT_FLAGS
---

# DXGI_DDI_PRESENT_FLAGS structure


## -description


Identifies how to perform a present operation.


## -syntax


````
typedef struct DXGI_DDI_PRESENT_FLAGS {
  union {
    struct {
      UINT Blt  :1;
      UINT Flip  :1;
      UINT PreferRight  :1;
      UINT TemporaryMono  :1;
      UINT Reserved  :28;
    };
    UINT   Value;
  };
} DXGI_DDI_PRESENT_FLAGS;
````


## -struct-fields




### -field Blt

Specifies whether to perform a bit-block transfer (bitblt) data to the primary surface. 

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field Flip

Specifies whether to flip to a new surface. 

Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).


### -field PreferRight

Supported in Windows 8 and later versions.

Specifies that, if a stereo present operation must be reduced to mono, the present operation should show the view from the right eye.

If this member is not set, the default mono present operation shows the view from the left eye.

Setting this member is equivalent to setting the third bit of the 32-bit <b>Value</b> member (0x00000004).


### -field TemporaryMono

Supported in Windows 8 and later versions.

Specifies that  a present operation should use the left buffer as a mono (non-stereo) buffer.

Setting this member is equivalent to setting the fourth bit of the 32-bit <b>Value</b> member (0x00000008).


### -field AllowTearing

 


### -field AllowFlexibleRefresh

 


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 28 bits (0xFFFFFFF0) of the 32-bit <b>Value</b> member to zeros.


### -field Value

A member in the union that is contained in DXGI_DDI_PRESENT_FLAGS that can hold one 32-bit value that identifies how to perform a present operation.


## -see-also

<a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_arg_present.md">DXGI_DDI_ARG_PRESENT</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569179">PresentDXGI</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGI_DDI_PRESENT_FLAGS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

