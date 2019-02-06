---
UID: NS:ntddvdeo._VIDEO_SHARE_MEMORY
title: _VIDEO_SHARE_MEMORY (ntddvdeo.h)
description: The VIDEO_SHARE_MEMORY structure is used in a request to the video miniport driver for a block of user-mode memory to be shared with the specified process.
old-location: display\video_share_memory.htm
tech.root: display
ms.assetid: 2339da67-78cd-49d4-a70c-fd774706fe3f
ms.date: 05/10/2018
ms.keywords: "*PVIDEO_SHARE_MEMORY, PVIDEO_SHARE_MEMORY, PVIDEO_SHARE_MEMORY structure pointer [Display Devices], VIDEO_SHARE_MEMORY, VIDEO_SHARE_MEMORY structure [Display Devices], Video_Structs_11e49bfc-ee25-48cd-9327-f09c6218ed72.xml, _VIDEO_SHARE_MEMORY, display.video_share_memory, ntddvdeo/PVIDEO_SHARE_MEMORY, ntddvdeo/VIDEO_SHARE_MEMORY"
ms.topic: struct
req.header: ntddvdeo.h
req.include-header: Ntddvdeo.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	ntddvdeo.h
api_name:
-	VIDEO_SHARE_MEMORY
product:
- Windows
targetos: Windows
req.typenames: VIDEO_SHARE_MEMORY, *PVIDEO_SHARE_MEMORY
---

# _VIDEO_SHARE_MEMORY structure


## -description


The VIDEO_SHARE_MEMORY structure is used in a request to the video miniport driver for a block of user-mode memory to be shared with the specified process.


## -struct-fields




### -field ProcessHandle

Is a handle to the current process. This member is usually set to <b>NtCurrentProcess</b>, a macro defined in <i>Ntddk.h</i>.


### -field ViewOffset

Indicates the byte offset from the beginning of the <a href="https://msdn.microsoft.com/f697e0db-1db0-4a81-94d8-0ca079885480">frame buffer</a>. This member is usually set to 0.


### -field ViewSize

Indicates the size, in bytes, of the frame buffer.


### -field RequestedVirtualAddress

Indicates the location of the requested frame buffer in the process's memory. This member is normally set to <b>NULL</b>, which means the display driver writer does not care about the precise location of the requested memory. If this member is set to a non-<b>NULL</b> value, the display driver writer intends that the frame buffer be located at that address. In this case, the display driver writer must be certain that the location specified is not already in use for another purpose.


## -remarks



VIDEO_SHARE_MEMORY is provided so that applications such as Direct Draw can have a view of video memory. Although the display driver is unable to directly provide such access to video memory, it can call into the video miniport driver for this purpose. The display driver does this by sending an <a href="https://msdn.microsoft.com/library/windows/hardware/ff568149">IOCTL_VIDEO_SHARE_VIDEO_MEMORY</a> request to the miniport driver. When the miniport driver fulfills this request, it uses the information in the VIDEO_SHARE_MEMORY structure, and fills in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff570549">VIDEO_SHARE_MEMORY_INFORMATION</a> structure with the actual location of the requested memory, if no location was specified. When the application no longer needs the shared memory, the display driver can release this memory by making an <a href="https://msdn.microsoft.com/library/windows/hardware/ff568155">IOCTL_VIDEO_UNSHARE_VIDEO_MEMORY</a> request, which also uses a VIDEO_SHARE_MEMORY structure as an input buffer.

For structures used in mapping into kernel-mode video memory, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff570506">VIDEO_MEMORY</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff570507">VIDEO_MEMORY_INFORMATION</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff568149">IOCTL_VIDEO_SHARE_VIDEO_MEMORY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568155">IOCTL_VIDEO_UNSHARE_VIDEO_MEMORY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570549">VIDEO_SHARE_MEMORY_INFORMATION</a>
 

 

