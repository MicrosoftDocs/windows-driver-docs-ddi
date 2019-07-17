---
UID: NC:video.PINT10_WRITE_MEMORY
title: PINT10_WRITE_MEMORY (video.h)
description: The Int10WriteMemory function writes the contents of an input buffer to memory in the context of another thread.
old-location: display\int10writememory.htm
tech.root: display
ms.assetid: a1143ca4-9c39-4bd7-92e1-473bdb447eb5
ms.date: 05/10/2018
ms.keywords: Int10WriteMemory, Int10WriteMemory callback function [Display Devices], PINT10_WRITE_MEMORY, PINT10_WRITE_MEMORY callback, VideoPort_Functions_6a882de2-2147-4b15-b4d8-6a87c49fa3d9.xml, display.int10writememory, video/Int10WriteMemory
ms.topic: callback
f1_keywords:
 - "video/Int10WriteMemory"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- video.h
api_name:
- Int10WriteMemory
product:
- Windows
targetos: Windows
req.typenames: 
---

# PINT10_WRITE_MEMORY callback function


## -description


The <i>Int10WriteMemory</i> function writes the contents of an input buffer to memory in the context of another thread.


## -parameters




### -param Context [in]

Pointer to a video port driver-defined context for the interface. This should be the same as the value in the <b>Context</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/ns-video-_video_port_int10_interface">VIDEO_PORT_INT10_INTERFACE</a> structure after <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nf-video-videoportqueryservices">VideoPortQueryServices</a> returns.


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



The video port implements this function, which can be accessed through a pointer in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/ns-video-_video_port_int10_interface">VIDEO_PORT_INT10_INTERFACE</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/ns-video-_video_port_int10_interface">VIDEO_PORT_INT10_INTERFACE</a>
 

 

