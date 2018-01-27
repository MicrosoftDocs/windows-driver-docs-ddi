---
UID: NS:ntddvdeo._VIDEO_SHARE_MEMORY_INFORMATION
title: _VIDEO_SHARE_MEMORY_INFORMATION
author: windows-driver-content
description: The VIDEO_SHARE_MEMORY_INFORMATION structure is used to communicate to the display driver that a request for a block of user-mode memory has been fulfilled.
old-location: display\video_share_memory_information.htm
old-project: display
ms.assetid: 004ecb65-a462-45e5-a647-9655727b202b
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.video_share_memory_information, ntddvdeo/PVIDEO_SHARE_MEMORY_INFORMATION, VIDEO_SHARE_MEMORY_INFORMATION structure [Display Devices], Video_Structs_bed1b1c4-1ee2-4f6b-862e-d6dd85d11e35.xml, ntddvdeo/VIDEO_SHARE_MEMORY_INFORMATION, PVIDEO_SHARE_MEMORY_INFORMATION structure pointer [Display Devices], _VIDEO_SHARE_MEMORY_INFORMATION, VIDEO_SHARE_MEMORY_INFORMATION, *PVIDEO_SHARE_MEMORY_INFORMATION, PVIDEO_SHARE_MEMORY_INFORMATION
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
-	VIDEO_SHARE_MEMORY_INFORMATION
product: Windows
targetos: Windows
req.typenames: *PVIDEO_SHARE_MEMORY_INFORMATION, VIDEO_SHARE_MEMORY_INFORMATION
---

# _VIDEO_SHARE_MEMORY_INFORMATION structure


## -description


The VIDEO_SHARE_MEMORY_INFORMATION structure is used to communicate to the display driver that a request for a block of user-mode memory has been fulfilled.


## -syntax


````
typedef struct _VIDEO_SHARE_MEMORY_INFORMATION {
  ULONG SharedViewOffset;
  ULONG SharedViewSize;
  PVOID VirtualAddress;
} VIDEO_SHARE_MEMORY_INFORMATION, *PVIDEO_SHARE_MEMORY_INFORMATION;
````


## -struct-fields




### -field SharedViewOffset

Indicates the offset, in bytes, from the beginning of the <a href="https://msdn.microsoft.com/f697e0db-1db0-4a81-94d8-0ca079885480">frame buffer</a>.


### -field SharedViewSize

Indicates the size, in bytes, of the frame buffer. The value of this member will always be a multiple of 64 KB.


### -field VirtualAddress

Indicates the address in virtual memory at which the requested memory was mapped.


## -remarks


When an application must have access to user-mode video memory, the display driver can call into the video miniport driver by sending it an <a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_share_video_memory.md">IOCTL_VIDEO_SHARE_VIDEO_MEMORY</a> request. The miniport driver uses a <a href="..\ntddvdeo\ns-ntddvdeo-_video_share_memory.md">VIDEO_SHARE_MEMORY</a> structure as an input buffer, and communicates back to the display driver a VIDEO_SHARE_MEMORY_INFORMATION structure. 

The video miniport driver fills out a VIDEO_SHARE_MEMORY_INFORMATION structure based on information in a VIDEO_SHARE_MEMORY structure. The following table summarizes how the information is used:
<table>
<tr>
<th>VIDEO_SHARE_MEMORY member</th>
<th>Result on VIDEO_SHARE_MEMORY_INFORMATION</th>
</tr>
<tr>
<td>
<b>ProcessHandle</b>

</td>
<td>
Is not used.

</td>
</tr>
<tr>
<td>
<b>ViewOffset</b>

</td>
<td>
Copied directly to <b>SharedViewOffset</b>.

</td>
</tr>
<tr>
<td>
<b>ViewSize</b>

</td>
<td>
Values that are multiples of 64 KB are copied directly to <b>SharedViewSize</b>. Other values are rounded up to the next larger multiple of 64 KB. 

</td>
</tr>
<tr>
<td>
<b>RequestedVirtualAddress</b>

</td>
<td>
If <b>NULL</b>, the miniport driver determines the address of a frame buffer to assign to <b>VirtualAddress</b>. If non-<b>NULL</b>, the miniport driver attempts to assign that value to <b>VirtualAddress</b>.

</td>
</tr>
</table> 



## -see-also

<a href="..\ntddvdeo\ns-ntddvdeo-_video_share_memory.md">VIDEO_SHARE_MEMORY</a>

<a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_share_video_memory.md">IOCTL_VIDEO_SHARE_VIDEO_MEMORY</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VIDEO_SHARE_MEMORY_INFORMATION structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

