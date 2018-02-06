---
UID: NS:d3dumddi._D3DDDIARG_VOLUMEBLT1
title: "_D3DDDIARG_VOLUMEBLT1"
author: windows-driver-content
description: Describes parameters for a volume bit-block transfer (bitblt) operation.
old-location: display\d3dddiarg_volumeblt1.htm
old-project: display
ms.assetid: 685aad54-03f5-4e3c-83a7-a44745acc4fb
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DDDIARG_VOLUMEBLT1, D3DDDIARG_VOLUMEBLT1 structure [Display Devices], _D3DDDIARG_VOLUMEBLT1, display.d3dddiarg_volumeblt1, d3dumddi/D3DDDIARG_VOLUMEBLT1
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
-	D3DDDIARG_VOLUMEBLT1
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_VOLUMEBLT1
---

# _D3DDDIARG_VOLUMEBLT1 structure


## -description


Describes parameters for a volume bit-block transfer (bitblt) operation.


## -syntax


````
typedef struct _D3DDDIARG_VOLUMEBLT1 {
  HANDLE    hDstResource;
  HANDLE    hSrcResource;
  UINT      DstX;
  UINT      DstY;
  UINT      DstZ;
  D3DDDIBOX SrcBox;
  UINT      CopyFlags;
} D3DDDIARG_VOLUMEBLT1;
````


## -struct-fields




### -field hDstResource

[in] A handle to the destination surface.


### -field hSrcResource

[in] A handle to the source surface.


### -field DstX

[in] The width, in screen coordinates, of the destination volume in which the source volume is copied.


### -field DstY

[in] The height, in screen coordinates, of the destination volume in which the source volume is copied.


### -field DstZ

[in] The depth, in screen coordinates, of the destination volume in which the source volume is copied.


### -field SrcBox

[in] A <a href="..\d3dumddi\ns-d3dumddi-_d3dddibox.md">D3DDDIBOX</a> structure that describes the source volume texture to copy to the destination.


### -field CopyFlags

A value that specifies characteristics of a copy operation as a bitwise OR of the values in the <a href="..\d3dumddi\ne-d3dumddi-d3dddi_copy_flags.md">D3DDDI_COPY_FLAGS</a> enumeration type.


## -see-also

<a href="..\d3dumddi\ne-d3dumddi-d3dddi_copy_flags.md">D3DDDI_COPY_FLAGS</a>

<a href="..\d3dumddi\ns-d3dumddi-_d3dddibox.md">D3DDDIBOX</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_VOLUMEBLT1 structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

