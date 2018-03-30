---
UID: NS:d3dukmdt._D3DDDI_RESOURCEFLAGS2
title: "_D3DDDI_RESOURCEFLAGS2"
author: windows-driver-content
description: Identifies the type of resource to create in a call to the driver's CreateResource2 function.
old-location: display\d3dddi_resourceflags2.htm
old-project: display
ms.assetid: 2edf2104-ad17-4c84-b991-57e64565029f
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDI_RESOURCEFLAGS2, D3DDDI_RESOURCEFLAGS2 structure [Display Devices], _D3DDDI_RESOURCEFLAGS2, d3dukmdt/D3DDDI_RESOURCEFLAGS2, display.d3dddi_resourceflags2
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3dukmdt.h
api_name:
-	D3DDDI_RESOURCEFLAGS2
product: Windows
targetos: Windows
req.typenames: D3DDDI_RESOURCEFLAGS2
---

# _D3DDDI_RESOURCEFLAGS2 structure


## -description


Identifies the type of resource to create in a call to the driver's <a href="https://msdn.microsoft.com/a8326707-cffc-4a20-ad3d-c7862661f513">CreateResource2</a> function.


## -struct-fields




### -field VideoEncoder

If set, indicates that the resource can be used as a capture buffer and/or a video encoder input resource.

If this member is set, the driver must set  either the <b>FORMATOP_CAPTURE</b> or <b>FORMATOP_VIDEO_ENCODER</b> flag values, or both, in the <b>Operations</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566438">FORMATOP</a> structure.

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




<a href="https://msdn.microsoft.com/a8326707-cffc-4a20-ad3d-c7862661f513">CreateResource2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566438">FORMATOP</a>
 

 

