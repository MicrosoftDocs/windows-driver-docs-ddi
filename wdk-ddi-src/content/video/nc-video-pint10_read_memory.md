---
UID: NC:video.PINT10_READ_MEMORY
title: PINT10_READ_MEMORY
author: windows-driver-content
description: The Int10ReadMemory function reads a block of memory in the context of another thread and stores it in an output buffer.
old-location: display\int10readmemory.htm
old-project: display
ms.assetid: 94b72ad0-1ace-4fde-a4a9-1078103e3d9b
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: display.int10readmemory, Int10ReadMemory callback function [Display Devices], Int10ReadMemory, PINT10_READ_MEMORY, PINT10_READ_MEMORY, video/Int10ReadMemory, VideoPort_Functions_fab5815b-1478-4d19-823f-05fd1de02b0c.xml
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
-	Int10ReadMemory
product: Windows
targetos: Windows
req.typenames: VHF_CONFIG, *PVHF_CONFIG
req.product: Windows 10 or later.
---

# PINT10_READ_MEMORY callback


## -description


The <i>Int10ReadMemory </i>function reads a block of memory in the context of another thread and stores it in an output buffer.


## -prototype


````
PINT10_READ_MEMORY Int10ReadMemory;

VP_STATUS Int10ReadMemory(
  _In_  PVOID  Context,
  _In_  USHORT Seg,
  _In_  USHORT Off,
  _Out_ PVOID  Buffer,
  _In_  ULONG  Length
)
{ ... }
````


## -parameters




### -param Context [in]

Pointer to a video port driver-defined context for the interface. This should be the same as the value in the <b>Context</b> member of the <a href="..\video\ns-video-_video_port_int10_interface.md">VIDEO_PORT_INT10_INTERFACE</a> structure after <a href="..\video\nf-video-videoportqueryservices.md">VideoPortQueryServices</a> returns.


### -param Seg [in]

Specifies the segment address of the buffer to be read.


### -param Off [in]

Specifies the offset within the segment indicated by the <i>Seg</i> parameter.


### -param Buffer [out]

Pointer to a memory location that indicates the beginning of the output buffer. 


### -param Length [in]

Is the length, in bytes, of the output buffer specified by the <i>Buffer</i> parameter.


## -returns



The <i>Int10ReadMemory</i> function returns NO_ERROR upon success. Otherwise it returns an appropriate error code.




## -remarks



The video port implements this function, which can be accessed through a pointer in the <a href="..\video\ns-video-_video_port_int10_interface.md">VIDEO_PORT_INT10_INTERFACE</a> structure.




## -see-also

<a href="..\video\ns-video-_video_port_int10_interface.md">VIDEO_PORT_INT10_INTERFACE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PINT10_READ_MEMORY callback function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

