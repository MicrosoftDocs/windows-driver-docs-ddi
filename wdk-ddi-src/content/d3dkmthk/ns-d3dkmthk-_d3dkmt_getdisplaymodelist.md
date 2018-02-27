---
UID: NS:d3dkmthk._D3DKMT_GETDISPLAYMODELIST
title: "_D3DKMT_GETDISPLAYMODELIST"
author: windows-driver-content
description: The D3DKMT_GETDISPLAYMODELIST structure describes a list of display modes.
old-location: display\d3dkmt_getdisplaymodelist.htm
old-project: display
ms.assetid: c937f1df-0221-4418-b48a-bcf0c41fa1e0
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3DKMT_GETDISPLAYMODELIST, D3DKMT_GETDISPLAYMODELIST structure [Display Devices], OpenGL_Structs_27c1c3f3-6316-4dc3-b83d-1a8f6f6360bb.xml, _D3DKMT_GETDISPLAYMODELIST, d3dkmthk/D3DKMT_GETDISPLAYMODELIST, display.d3dkmt_getdisplaymodelist
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
-	D3DKMT_GETDISPLAYMODELIST
product: Windows
targetos: Windows
req.typenames: D3DKMT_GETDISPLAYMODELIST
---

# _D3DKMT_GETDISPLAYMODELIST structure


## -description


The D3DKMT_GETDISPLAYMODELIST structure describes a list of display modes.


## -syntax


````
typedef struct _D3DKMT_GETDISPLAYMODELIST {
  D3DKMT_HANDLE                  hAdapter;
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
  D3DKMT_DISPLAYMODE             *pModeList;
  UINT                           ModeCount;
} D3DKMT_GETDISPLAYMODELIST;
````


## -struct-fields




### -field hAdapter

[in] A handle to the graphics adapter.


### -field VidPnSourceId

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology that the display modes apply to.


### -field pModeList

[out] An array of <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_displaymode.md">D3DKMT_DISPLAYMODE</a> structures that represent the list of display modes.


### -field ModeCount

[in/out] The number of display modes in the array that <b>pModeList</b> specifies.


## -see-also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtgetdisplaymodelist.md">D3DKMTGetDisplayModeList</a>



<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_displaymode.md">D3DKMT_DISPLAYMODE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_GETDISPLAYMODELIST structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

