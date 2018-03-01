---
UID: NS:d3dkmthk._D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT
title: "_D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT"
author: windows-driver-content
description: The D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT structure describes the private-format attribute to set for a video present source.
old-location: display\d3dkmt_setdisplayprivatedriverformat.htm
old-project: display
ms.assetid: a99a3b15-8c91-4aef-a82c-665c8494fa57
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT, D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT structure [Display Devices], OpenGL_Structs_c5440fbe-47f2-43eb-ae09-e9295bfa4bad.xml, _D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT, d3dkmthk/D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT, display.d3dkmt_setdisplayprivatedriverformat
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
-	D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT
product: Windows
targetos: Windows
req.typenames: D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT
---

# _D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT structure


## -description


The D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT structure describes the private-format attribute to set for a video present source. 


## -syntax


````
typedef struct _D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT {
  D3DKMT_HANDLE                  hDevice;
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
  UINT                           PrivateDriverFormatAttribute;
} D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT;
````


## -struct-fields




### -field hDevice

[in] A handle to the device that requests to change the private-format attribute of a video present source.


### -field VidPnSourceId

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology to set a private-format attribute on (that is, the identifier of the primary surface to set a private-format attribute on). 


### -field PrivateDriverFormatAttribute

[in] A UINT value that specifies the private-format attribute to set for the video present source that the <b>VidPnSourceId</b> member specifies. 


## -see-also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtsetdisplayprivatedriverformat.md">D3DKMTSetDisplayPrivateDriverFormat</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

