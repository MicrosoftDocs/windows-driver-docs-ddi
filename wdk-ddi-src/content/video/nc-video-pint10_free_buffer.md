---
UID: NC:video.PINT10_FREE_BUFFER
title: PINT10_FREE_BUFFER
author: windows-driver-content
description: The Int10FreeBuffer function frees a buffer previously allocated by Int10AllocateBuffer.
old-location: display\int10freebuffer.htm
old-project: display
ms.assetid: feb7dd98-8c44-405e-8e98-ffd6246cf0ee
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.int10freebuffer, Int10FreeBuffer callback function [Display Devices], Int10FreeBuffer, PINT10_FREE_BUFFER, PINT10_FREE_BUFFER, video/Int10FreeBuffer, VideoPort_Functions_607fc1f2-1d9a-48eb-97c2-a2cd510e3d78.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating systems.
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	video.h
apiname:
-	Int10FreeBuffer
product: Windows
targetos: Windows
req.typenames: VHF_CONFIG, *PVHF_CONFIG
---

# PINT10_FREE_BUFFER callback


## -description


The <i>Int10FreeBuffer</i> function frees a buffer previously allocated by <i>Int10AllocateBuffer</i>.


## -prototype


````
PINT10_FREE_BUFFER Int10FreeBuffer;

VP_STATUS Int10FreeBuffer(
  _In_ PVOID  Context,
  _In_ USHORT Seg,
  _In_ USHORT Off
)
{ ... }
````


## -parameters




### -param Context [in]

Pointer to a video port driver-defined context for the interface. This should be the same as the value in the <b>Context</b> member of the <a href="..\video\ns-video-_video_port_int10_interface.md">VIDEO_PORT_INT10_INTERFACE</a> structure after <a href="..\video\nf-video-videoportqueryservices.md">VideoPortQueryServices</a> returns.


### -param Seg [in]

Specifies the segment address of the buffer to be freed.


### -param Off [in]

Specifies the offset within the segment indicated by the <i>Seg</i> parameter.


## -returns


The <i>Int10FreeBuffer</i> function returns NO_ERROR upon success. Otherwise, the function returns an appropriate error code.



## -remarks


The video port implements this function, which can be accessed through a pointer in the <a href="..\video\ns-video-_video_port_int10_interface.md">VIDEO_PORT_INT10_INTERFACE</a> structure.



## -see-also

<a href="..\video\ns-video-_video_port_int10_interface.md">VIDEO_PORT_INT10_INTERFACE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PINT10_FREE_BUFFER callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

