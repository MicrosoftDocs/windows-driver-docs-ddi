---
UID: NS:d3dukmdt._D3DDDI_RESOURCEFLAGS2
title: "_D3DDDI_RESOURCEFLAGS2"
author: windows-driver-content
description: Identifies the type of resource to create in a call to the driver's CreateResource2 function.
old-location: display\d3dddi_resourceflags2.htm
old-project: display
ms.assetid: 2edf2104-ad17-4c84-b991-57e64565029f
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , ,, 2, 3, A, C, D, D3DDDI_RESOURCEFLAGS2, D3DDDI_RESOURCEFLAGS2 structure [Display Devices], E, F, G, I, L, O, R, S, U, _, _D3DDDI_RESOURCEFLAGS2, d3dukmdt/D3DDDI_RESOURCEFLAGS2, display.d3dddi_resourceflags2"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dukmdt.h
req.include-header: D3dukmdt.h, D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	D3dukmdt.h
apiname:
-	D3DDDI_RESOURCEFLAGS2
product: Windows
targetos: Windows
req.typenames: D3DDDI_RESOURCEFLAGS2
---

# _D3DDDI_RESOURCEFLAGS2 structure


## -description


Identifies the type of resource to create in a call to the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createresource2.md">CreateResource2</a> function.


## -syntax


````
typedef struct _D3DDDI_RESOURCEFLAGS2 {
  union {
    struct {
      UINT VideoEncoder  :1;
      UINT UserMemory  :1;
#if ((DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM1_3) || \
     (D3D_UMD_INTERFACE_VERSION >= D3D_UMD_INTERFACE_VERSION_WDDM1_3))
      UINT CrossAdapter  :1;
      UINT Reserved  :29;
#else 
      UINT Reserved  :30;
#endif 
    };
    UINT   Value;
  };
} D3DDDI_RESOURCEFLAGS2;
````


## -struct-fields




### -field VideoEncoder

If set, indicates that the resource can be used as a capture buffer and/or a video encoder input resource.

If this member is set, the driver must set  either the <b>FORMATOP_CAPTURE</b> or <b>FORMATOP_VIDEO_ENCODER</b> flag values, or both, in the <b>Operations</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_formatop.md">FORMATOP</a> structure.

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field UserMemory

If set, indicates that the memory for this surface was allocated by the application, not by the Direct3D runtime.

Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).


### -field CrossAdapter

If set, indicates that the resource is  a shared cross-adapter resource.

Setting this member is equivalent to setting the third bit of the 32-bit <b>Value</b> member (0x00000004).

Supported starting with Windows 8.1.


### -field IsDisplayable

 


### -field Reserved

Reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 29 bits (0xFFFFFFF8) of the 32-bit <b>Value</b> member to zeros.

Supported starting with Windows 8.1.

Reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 30 bits (0xFFFFFFFC) of the 32-bit <b>Value</b> member to zeros.


#### - Value

A 32-bit value that identifies the type of resource to create.


## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_formatop.md">FORMATOP</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createresource2.md">CreateResource2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_RESOURCEFLAGS2 structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

