---
UID: NF:video.VideoPortLockPages
title: VideoPortLockPages function
author: windows-driver-content
description: The VideoPortLockPages function is obsolete in Windows 2000 and later. Use VideoPortLockBuffer in place of this function.VideoPortLockPages locks the specified virtual memory and possibly performs part or all of a DMA transfer.
old-location: display\videoportlockpages.htm
old-project: display
ms.assetid: f5e06ff3-98ba-4443-8ea6-c32b063cd478
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , L, P, V, VideoPortLockPages, VideoPortLockPages function [Display Devices], VideoPort_Functions_47b202e0-2a8b-4fb0-9cf2-b4ef3ddb9ff4.xml, a, c, d, display.videoportlockpages, e, g, i, k, o, r, s, t, video/VideoPortLockPages"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: Videoprt.lib
req.dll: Videoprt.sys
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Videoprt.sys
apiname:
-	VideoPortLockPages
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortLockPages function


## -description


The <b>VideoPortLockPages</b> function is <b>obsolete</b> in Windows 2000 and later. Use <a href="..\video\nf-video-videoportlockbuffer.md">VideoPortLockBuffer</a> in place of this function.

<b>VideoPortLockPages</b> locks the specified virtual memory and possibly performs part or all of a DMA transfer.


## -syntax


````
BOOLEAN VideoPortLockPages(
  _In_    PVOID                 HwDeviceExtension,
  _Inout_ PVIDEO_REQUEST_PACKET pVrp,
  _In_    PEVENT                pUEvent,
  _In_    PEVENT                pDisplayEvent,
  _In_    DMA_FLAGS             DmaFlags
);
````


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param pVrp [in, out]

Pointer to a <a href="..\video\ns-video-_video_request_packet.md">VIDEO_REQUEST_PACKET</a> structure. The miniport driver must have set <b>InputBuffer</b> and <b>InputBufferLength</b> to contain the virtual address and the size in bytes, respectively, of the memory to be locked for the transfer. This memory was allocated by the display driver and passed to the miniport driver through an IOCTL. The video port returns a pointer to and the size in bytes of the scatter/gather list in <b>OutputBuffer</b> and <b>OutputBufferLength</b>, respectively.


### -param pUEvent [in]

Pointer to a mapped user event that is to be set by the miniport driver, or <b>NULL</b>. The user event was mapped by the display driver and passed to the miniport driver through an IOCTL.


### -param pDisplayEvent [in]

Pointer to an event that is to be set by the miniport driver, or <b>NULL</b>. This event was created by and received from the display driver through an IOCTL.


### -param DmaFlags [in]

Specifies the action to be performed. This parameter must be one of the following values:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>VideoPortDmaInitOnly</b>

</td>
<td>
<b>VideoPortLockPages</b> locks the requested memory.

</td>
</tr>
<tr>
<td>
<b>VideoPortKeepPagesLocked</b>

</td>
<td>
<b>VideoPortLockPages</b> takes no action.

</td>
</tr>
<tr>
<td>
<b>VideoPortUnlockAfterDma</b>

</td>
<td>
<b>VideoPortLockPages</b> takes no action.

</td>
</tr>
</table>
 


## -returns



<b>VideoPortLockPages</b> returns <b>TRUE</b> upon successful completion of the action requested of it. It returns <b>FALSE</b> if the <i>DmaFlags</i> parameter is not equal to <b>VideoPortDmaInitOnly</b>.




## -remarks



See <a href="https://msdn.microsoft.com/fe6c2e16-d222-4948-b1df-34ed8d57d9d8">Bus-Master DMA in Video Miniport Drivers</a> for information about packet-based and common-buffer DMA transfers.

<b>VideoPortLockPages</b> cannot be called from an ISR or DPC.




## -see-also

<a href="..\video\nf-video-videoportlockbuffer.md">VideoPortLockBuffer</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortLockPages function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

