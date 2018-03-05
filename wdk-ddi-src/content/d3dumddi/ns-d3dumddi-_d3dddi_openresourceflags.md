---
UID: NS:d3dumddi._D3DDDI_OPENRESOURCEFLAGS
title: "_D3DDDI_OPENRESOURCEFLAGS"
author: windows-driver-content
description: The D3DDDI_OPENRESOURCEFLAGS structure identifies the type of resource to open.
old-location: display\d3dddi_openresourceflags.htm
old-project: display
ms.assetid: f65fda13-3d05-4e1b-b0c7-01e43a9bf09e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDI_OPENRESOURCEFLAGS, D3DDDI_OPENRESOURCEFLAGS structure [Display Devices], D3D_other_Structs_918a41c9-09de-4916-a0d6-fd69f7c431c2.xml, _D3DDDI_OPENRESOURCEFLAGS, d3dumddi/D3DDDI_OPENRESOURCEFLAGS, display.d3dddi_openresourceflags
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	D3DDDI_OPENRESOURCEFLAGS
product: Windows
targetos: Windows
req.typenames: D3DDDI_OPENRESOURCEFLAGS
---

# _D3DDDI_OPENRESOURCEFLAGS structure


## -description


The D3DDDI_OPENRESOURCEFLAGS structure identifies the type of resource to open.


## -syntax


````
typedef struct _D3DDDI_OPENRESOURCEFLAGS {
  union {
    struct {
      UINT Fullscreen  :1;
      UINT AlphaOverride  :1;
      UINT Reserved  :30;
    };
    UINT   Value;
  };
} D3DDDI_OPENRESOURCEFLAGS;
````


## -struct-fields




### -field Fullscreen

A UINT value that specifies whether the shared primary resource is used with a full-screen device.

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field AlphaOverride

A UINT value that specifies whether to use the alpha channel in the shared primary resource. If <b>AlphaOverride</b> is set, the alpha channel should not be used.

Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 30 bits (0xFFFFFFFC) of the 32-bit <b>Value</b> member to zeros.


#### - Value

A member in the union that is contained in D3DDDI_OPENRESOURCEFLAGS that can hold one 32-bit value that identifies the type of resource to open.


## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_openresource.md">D3DDDIARG_OPENRESOURCE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_OPENRESOURCEFLAGS structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

