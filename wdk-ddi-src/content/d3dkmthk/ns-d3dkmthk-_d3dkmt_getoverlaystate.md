---
UID: NS:d3dkmthk._D3DKMT_GETOVERLAYSTATE
title: "_D3DKMT_GETOVERLAYSTATE"
author: windows-driver-content
description: The D3DKMT_GETOVERLAYSTATE structure describes parameters that the D3DKMTGetOverlayState function uses to retrieve status about an overlay.
old-location: display\d3dkmt_getoverlaystate.htm
old-project: display
ms.assetid: fe3443e7-0dc9-4c91-88ab-b05bac19516d
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: D3DKMT_GETOVERLAYSTATE structure [Display Devices], _D3DKMT_GETOVERLAYSTATE, d3dkmthk/D3DKMT_GETOVERLAYSTATE, D3DKMT_GETOVERLAYSTATE, OpenGL_Structs_c9bee52b-d6ba-45ee-9af6-b795685715bb.xml, display.d3dkmt_getoverlaystate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: D3DKMT_GETOVERLAYSTATE is supported beginning with the Windows 7 operating system.
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
-	D3DKMT_GETOVERLAYSTATE
product: Windows
targetos: Windows
req.typenames: D3DKMT_GETOVERLAYSTATE
---

# _D3DKMT_GETOVERLAYSTATE structure


## -description


The D3DKMT_GETOVERLAYSTATE structure describes parameters that the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtgetoverlaystate.md">D3DKMTGetOverlayState</a> function uses to retrieve status about an overlay. 


## -syntax


````
typedef struct _D3DKMT_GETOVERLAYSTATE {
  D3DKMT_HANDLE hDevice;
  D3DKMT_HANDLE hOverlay;
  BOOLEAN       OverlayEnabled;
} D3DKMT_GETOVERLAYSTATE;
````


## -struct-fields




### -field hDevice

[in] A D3DKMT_HANDLE data type that represents the kernel-mode handle to the device that the overlay is associated with.


### -field hOverlay

[in] A D3DKMT_HANDLE data type that represents the kernel-mode handle that is returned by the create-overlay function and that identifies the kernel-mode overlay object to retrieve status about. 


### -field OverlayEnabled

[out] A Boolean variable that receives <b>TRUE</b> if the overlay is enabled and <b>FALSE</b> if the overlay is disabled. 


## -see-also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtgetoverlaystate.md">D3DKMTGetOverlayState</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_GETOVERLAYSTATE structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

