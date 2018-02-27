---
UID: NS:d3dkmthk._D3DKMT_WAITFORVERTICALBLANKEVENT
title: "_D3DKMT_WAITFORVERTICALBLANKEVENT"
author: windows-driver-content
description: The D3DKMT_WAITFORVERTICALBLANKEVENT structure describes parameters for waiting for the vertical blanking interval to occur.
old-location: display\d3dkmt_waitforverticalblankevent.htm
old-project: display
ms.assetid: dde8ebf7-7839-4bcc-8cb1-02a5ca922792
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3DKMT_WAITFORVERTICALBLANKEVENT, D3DKMT_WAITFORVERTICALBLANKEVENT structure [Display Devices], OpenGL_Structs_1072adb2-825b-4fee-a84a-b958e3d2e4d4.xml, _D3DKMT_WAITFORVERTICALBLANKEVENT, d3dkmthk/D3DKMT_WAITFORVERTICALBLANKEVENT, display.d3dkmt_waitforverticalblankevent
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
-	D3DKMT_WAITFORVERTICALBLANKEVENT
product: Windows
targetos: Windows
req.typenames: D3DKMT_WAITFORVERTICALBLANKEVENT
---

# _D3DKMT_WAITFORVERTICALBLANKEVENT structure


## -description


The D3DKMT_WAITFORVERTICALBLANKEVENT structure describes parameters for waiting for the vertical blanking interval to occur.


## -syntax


````
typedef struct _D3DKMT_WAITFORVERTICALBLANKEVENT {
  D3DKMT_HANDLE                  hAdapter;
  D3DKMT_HANDLE                  hDevice;
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
} D3DKMT_WAITFORVERTICALBLANKEVENT;
````


## -struct-fields




### -field hAdapter

[in] A handle to the adapter.


### -field hDevice

[in] A handle to the display device. This member is optionally specified. However, if the OpenGL ICD specifies the display device, the kernel is given more optimization opportunities with regard to power usage. 


### -field VidPnSourceId

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology for the VidPN source. 


## -see-also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtwaitforverticalblankevent.md">D3DKMTWaitForVerticalBlankEvent</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_WAITFORVERTICALBLANKEVENT structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

