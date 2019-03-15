---
UID: NF:video.VideoPortLockBuffer
title: VideoPortLockBuffer function (video.h)
description: The VideoPortLockBuffer function probes the specified buffer, makes the buffer's memory pages resident in memory, and locks the physical pages mapped by the virtual address range.
old-location: display\videoportlockbuffer.htm
tech.root: display
ms.assetid: ba65d1b1-a720-4f21-8c6d-af70185c0c24
ms.date: 05/10/2018
ms.keywords: VideoPortLockBuffer, VideoPortLockBuffer function [Display Devices], VideoPort_Functions_8c96bd4d-b9fc-4ff7-9d81-1087d6527700.xml, display.videoportlockbuffer, video/VideoPortLockBuffer
ms.topic: function
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP and later versions of the Windows operating systems.
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
req.lib: Videoprt.lib
req.dll: Videoprt.sys
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Videoprt.sys
api_name:
- VideoPortLockBuffer
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortLockBuffer function


## -description


The <b>VideoPortLockBuffer</b> function probes the specified buffer, makes the buffer's memory pages resident in memory, and locks the physical pages mapped by the virtual address range.


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param BaseAddress [in]

Specifies the virtual address of the buffer to be locked.


### -param Length [in]

Specifies the length in bytes of the buffer to be locked.


### -param Operation [in]

Specifies the type of operation for which the caller wants the access rights probed and the pages locked. The operation can be one of the following: <b>VpReadAccess</b>, <b>VpWriteAccess</b>, or <b>VpModifyAccess</b>.


## -returns



Returns a pointer to a memory descriptor list (<a href="https://msdn.microsoft.com/library/windows/hardware/ff554414">MDL</a>), or a <b>NULL</b> pointer if the MDL for the memory to be locked cannot be allocated.




## -remarks



To unlock the buffer, the video miniport driver should call <a href="https://msdn.microsoft.com/library/windows/hardware/ff570373">VideoPortUnlockBuffer</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff570373">VideoPortUnlockBuffer</a>
 

 

