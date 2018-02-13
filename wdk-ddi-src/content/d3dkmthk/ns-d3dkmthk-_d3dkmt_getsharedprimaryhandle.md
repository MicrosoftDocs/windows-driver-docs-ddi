---
UID: NS:d3dkmthk._D3DKMT_GETSHAREDPRIMARYHANDLE
title: "_D3DKMT_GETSHAREDPRIMARYHANDLE"
author: windows-driver-content
description: The D3DKMT_GETSHAREDPRIMARYHANDLE structure describes the parameters that are required to retrieve the global shared handle for the primary surface.
old-location: display\d3dkmt_getsharedprimaryhandle.htm
old-project: display
ms.assetid: 59c45a0e-54c3-4301-8e65-409d6c728325
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMT_GETSHAREDPRIMARYHANDLE structure [Display Devices], d3dkmthk/D3DKMT_GETSHAREDPRIMARYHANDLE, D3DKMT_GETSHAREDPRIMARYHANDLE, OpenGL_Structs_322563d8-5546-4b10-bd74-101f3ffb633a.xml, _D3DKMT_GETSHAREDPRIMARYHANDLE, display.d3dkmt_getsharedprimaryhandle
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
-	D3DKMT_GETSHAREDPRIMARYHANDLE
product: Windows
targetos: Windows
req.typenames: D3DKMT_GETSHAREDPRIMARYHANDLE
---

# _D3DKMT_GETSHAREDPRIMARYHANDLE structure


## -description


The D3DKMT_GETSHAREDPRIMARYHANDLE structure describes the parameters that are required to retrieve the global shared handle for the primary surface.


## -syntax


````
typedef struct _D3DKMT_GETSHAREDPRIMARYHANDLE {
  D3DKMT_HANDLE                  hAdapter;
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
  D3DKMT_HANDLE                  hSharedPrimary;
} D3DKMT_GETSHAREDPRIMARYHANDLE;
````


## -struct-fields




### -field hAdapter

[in] A handle to the graphics adapter that the primary surface is associated with.


### -field VidPnSourceId

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology that displays the primary surface.


### -field hSharedPrimary

[out] A handle to the global shared primary surface if a shared handle currently exists. The shared handle is returned from the call to the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtgetsharedprimaryhandle.md">D3DKMTGetSharedPrimaryHandle</a> function.


## -see-also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtgetsharedprimaryhandle.md">D3DKMTGetSharedPrimaryHandle</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_GETSHAREDPRIMARYHANDLE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

