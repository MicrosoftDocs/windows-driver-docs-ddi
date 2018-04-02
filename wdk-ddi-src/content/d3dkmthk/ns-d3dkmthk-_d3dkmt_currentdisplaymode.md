---
UID: NS:d3dkmthk._D3DKMT_CURRENTDISPLAYMODE
title: "_D3DKMT_CURRENTDISPLAYMODE"
author: windows-driver-content
description: The D3DKMT_CURRENTDISPLAYMODE structure describes the current display mode of the specified video source.
old-location: display\d3dkmt_currentdisplaymode.htm
old-project: display
ms.assetid: 8ba027f9-3671-461c-bae6-2da0059cf0ab
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMT_CURRENTDISPLAYMODE, D3DKMT_CURRENTDISPLAYMODE structure [Display Devices], OpenGL_Structs_9af2b5dc-c342-4644-a3db-db9649b1fc9c.xml, _D3DKMT_CURRENTDISPLAYMODE, d3dkmthk/D3DKMT_CURRENTDISPLAYMODE, display.d3dkmt_currentdisplaymode
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
-	D3DKMT_CURRENTDISPLAYMODE
product:
- Windows
targetos: Windows
req.typenames: D3DKMT_CURRENTDISPLAYMODE
---

# _D3DKMT_CURRENTDISPLAYMODE structure


## -description


The D3DKMT_CURRENTDISPLAYMODE structure describes the current display mode of the specified video source. 


## -struct-fields




### -field VidPnSourceId

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology that the display mode applies to.


### -field DisplayMode

[out] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff547942">D3DKMT_DISPLAYMODE</a> structure that represents the current display mode.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547100">D3DKMTQueryAdapterInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547942">D3DKMT_DISPLAYMODE</a>
 

 

