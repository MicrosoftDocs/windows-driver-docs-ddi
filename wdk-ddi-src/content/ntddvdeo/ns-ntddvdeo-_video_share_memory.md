---
UID: NS:ntddvdeo._VIDEO_SHARE_MEMORY
title: _VIDEO_SHARE_MEMORY
author: windows-driver-content
description: The VIDEO_SHARE_MEMORY structure is used in a request to the video miniport driver for a block of user-mode memory to be shared with the specified process.
old-location: display\video_share_memory.htm
old-project: display
ms.assetid: 2339da67-78cd-49d4-a70c-fd774706fe3f
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: PVIDEO_SHARE_MEMORY structure pointer [Display Devices], _VIDEO_SHARE_MEMORY, ntddvdeo/PVIDEO_SHARE_MEMORY, ntddvdeo/VIDEO_SHARE_MEMORY, VIDEO_SHARE_MEMORY, Video_Structs_11e49bfc-ee25-48cd-9327-f09c6218ed72.xml, display.video_share_memory, PVIDEO_SHARE_MEMORY, *PVIDEO_SHARE_MEMORY, VIDEO_SHARE_MEMORY structure [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	ntddvdeo.h
apiname: 
-	VIDEO_SHARE_MEMORY
product: Windows
targetos: Windows
req.typenames: *PVIDEO_SHARE_MEMORY, VIDEO_SHARE_MEMORY
---

# _VIDEO_SHARE_MEMORY structure


## -description


The VIDEO_SHARE_MEMORY structure is used in a request to the video miniport driver for a block of user-mode memory to be shared with the specified process.


## -syntax


````
typedef struct _VIDEO_SHARE_MEMORY {
  HANDLE ProcessHandle;
  ULONG  ViewOffset;
  ULONG  ViewSize;
  PVOID  RequestedVirtualAddress;
} VIDEO_SHARE_MEMORY, *PVIDEO_SHARE_MEMORY;
````


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


VIDEO_SHARE_MEMORY is provided so that applications such as Direct Draw can have a view of video memory. Although the display driver is unable to directly provide such access to video memory, it can call into the video miniport driver for this purpose. The display driver does this by sending an <a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_share_video_memory.md">IOCTL_VIDEO_SHARE_VIDEO_MEMORY</a> request to the miniport driver. When the miniport driver fulfills this request, it uses the information in the VIDEO_SHARE_MEMORY structure, and fills in a <a href="..\ntddvdeo\ns-ntddvdeo-_video_share_memory_information.md">VIDEO_SHARE_MEMORY_INFORMATION</a> structure with the actual location of the requested memory, if no location was specified. When the application no longer needs the shared memory, the display driver can release this memory by making an <a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_unshare_video_memory.md">IOCTL_VIDEO_UNSHARE_VIDEO_MEMORY</a> request, which also uses a VIDEO_SHARE_MEMORY structure as an input buffer.

For structures used in mapping into kernel-mode video memory, see <a href="..\ntddvdeo\ns-ntddvdeo-_video_memory.md">VIDEO_MEMORY</a> and <a href="..\ntddvdeo\ns-ntddvdeo-_video_memory_information.md">VIDEO_MEMORY_INFORMATION</a>.



## -see-also

<a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_share_video_memory.md">IOCTL_VIDEO_SHARE_VIDEO_MEMORY</a>

<a href="..\ntddvdeo\ns-ntddvdeo-_video_share_memory_information.md">VIDEO_SHARE_MEMORY_INFORMATION</a>

<a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_unshare_video_memory.md">IOCTL_VIDEO_UNSHARE_VIDEO_MEMORY</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VIDEO_SHARE_MEMORY structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

