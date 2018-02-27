---
UID: NS:d3dumddi._D3DDDIARG_TEXBLT1
title: "_D3DDDIARG_TEXBLT1"
author: windows-driver-content
description: Describes parameters for a texture bit-block transfer (bitblt) operation.
old-location: display\d3dddiarg_texblt1.htm
old-project: display
ms.assetid: e11fd9b5-c3ad-4f8f-890c-30ca5ce4a57f
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3DDDIARG_TEXBLT1, D3DDDIARG_TEXBLT1 structure [Display Devices], _D3DDDIARG_TEXBLT1, d3dumddi/D3DDDIARG_TEXBLT1, display.d3dddiarg_texblt1
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
-	D3dumddi.h
apiname:
-	D3DDDIARG_TEXBLT1
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_TEXBLT1
---

# _D3DDDIARG_TEXBLT1 structure


## -description


Describes parameters for a texture bit-block transfer (bitblt) operation.


## -syntax


````
typedef struct _D3DDDIARG_TEXBLT1 {
  HANDLE hDstResource;
  HANDLE hSrcResource;
  UINT   CubeMapFace;
  POINT  DstPoint;
  RECT   SrcRect;
  UINT   CopyFlags;
} D3DDDIARG_TEXBLT1;
````


## -struct-fields




### -field hDstResource

A handle to the destination resource.


### -field hSrcResource

A handle to the source resource.


### -field CubeMapFace

The face of a cube map.


### -field DstPoint

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff569161">POINT</a> structure that describes the destination point where the source texture is copied.


### -field SrcRect

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure that describes the source texture to copy to the destination point.


### -field CopyFlags

A value that specifies characteristics of a copy operation as a bitwise OR of the values in the <a href="..\d3dumddi\ne-d3dumddi-d3dddi_copy_flags.md">D3DDDI_COPY_FLAGS</a> enumeration type.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>



<a href="..\d3dumddi\ne-d3dumddi-d3dddi_copy_flags.md">D3DDDI_COPY_FLAGS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569161">POINT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_TEXBLT1 structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

