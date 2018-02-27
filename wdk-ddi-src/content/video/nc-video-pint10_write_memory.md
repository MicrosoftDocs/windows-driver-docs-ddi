---
UID: NC:video.PINT10_WRITE_MEMORY
title: PINT10_WRITE_MEMORY
author: windows-driver-content
description: The Int10WriteMemory function writes the contents of an input buffer to memory in the context of another thread.
old-location: display\int10writememory.htm
old-project: display
ms.assetid: a1143ca4-9c39-4bd7-92e1-473bdb447eb5
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: Int10WriteMemory, Int10WriteMemory callback function [Display Devices], PINT10_WRITE_MEMORY, VideoPort_Functions_6a882de2-2147-4b15-b4d8-6a87c49fa3d9.xml, display.int10writememory, video/Int10WriteMemory
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
-	Int10WriteMemory
product: Windows
targetos: Windows
req.typenames: VHF_CONFIG, *PVHF_CONFIG
req.product: Windows 10 or later.
---

# PINT10_WRITE_MEMORY callback


## -description


The <i>Int10WriteMemory</i> function writes the contents of an input buffer to memory in the context of another thread.


## -prototype


````
PINT10_WRITE_MEMORY Int10WriteMemory;

VP_STATUS Int10WriteMemory(
  _In_ PVOID  Context,
  _In_ USHORT Seg,
  _In_ USHORT Off,
  _In_ PVOID  Buffer,
  _In_ ULONG  Length
)
{ ... }
````


## -parameters




### -param Context [in]

Pointer to a video port driver-defined context for the interface. This should be the same as the value in the <b>Context</b> member of the <a href="..\video\ns-video-_video_port_int10_interface.md">VIDEO_PORT_INT10_INTERFACE</a> structure after <a href="..\video\nf-video-videoportqueryservices.md">VideoPortQueryServices</a> returns.


### -param Seg [in]

Specifies the segment address of the buffer to be written.


### -param Off [in]

Specifies the offset within the segment indicated by the <i>Seg</i> parameter.


### -param Buffer [in]

Pointer to the memory location that marks the beginning of the input buffer.


### -param Length [in]

Is the length, in bytes, of the input buffer specified by the <i>Buffer</i> parameter.


## -returns



The <i>Int10WriteMemory</i> function returns NO_ERROR upon success. Otherwise it returns an appropriate error code.




## -remarks



The video port implements this function, which can be accessed through a pointer in the <a href="..\video\ns-video-_video_port_int10_interface.md">VIDEO_PORT_INT10_INTERFACE</a> structure.




## -see-also

<a href="..\video\ns-video-_video_port_int10_interface.md">VIDEO_PORT_INT10_INTERFACE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PINT10_WRITE_MEMORY callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

