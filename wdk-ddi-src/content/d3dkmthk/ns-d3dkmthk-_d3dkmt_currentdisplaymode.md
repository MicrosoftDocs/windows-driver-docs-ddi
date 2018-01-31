---
UID: NS:d3dkmthk._D3DKMT_CURRENTDISPLAYMODE
title: "_D3DKMT_CURRENTDISPLAYMODE"
author: windows-driver-content
description: The D3DKMT_CURRENTDISPLAYMODE structure describes the current display mode of the specified video source.
old-location: display\d3dkmt_currentdisplaymode.htm
old-project: display
ms.assetid: 8ba027f9-3671-461c-bae6-2da0059cf0ab
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMT_CURRENTDISPLAYMODE, D3DKMT_CURRENTDISPLAYMODE structure [Display Devices], display.d3dkmt_currentdisplaymode, OpenGL_Structs_9af2b5dc-c342-4644-a3db-db9649b1fc9c.xml, _D3DKMT_CURRENTDISPLAYMODE, d3dkmthk/D3DKMT_CURRENTDISPLAYMODE
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmthk.h
apiname:
-	D3DKMT_CURRENTDISPLAYMODE
product: Windows
targetos: Windows
req.typenames: D3DKMT_CURRENTDISPLAYMODE
---

# _D3DKMT_CURRENTDISPLAYMODE structure


## -description


The D3DKMT_CURRENTDISPLAYMODE structure describes the current display mode of the specified video source. 


## -syntax


````
typedef struct _D3DKMT_CURRENTDISPLAYMODE {
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
  D3DKMT_DISPLAYMODE             DisplayMode;
} D3DKMT_CURRENTDISPLAYMODE;
````


## -struct-fields




#### - VidPnSourceId

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology that the display mode applies to.


#### - DisplayMode

[out] A <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_displaymode.md">D3DKMT_DISPLAYMODE</a> structure that represents the current display mode.


## -see-also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtqueryadapterinfo.md">D3DKMTQueryAdapterInfo</a>

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_displaymode.md">D3DKMT_DISPLAYMODE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_CURRENTDISPLAYMODE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

