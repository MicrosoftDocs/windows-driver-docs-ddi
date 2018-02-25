---
UID: NF:video.VideoPortDoDma
title: VideoPortDoDma function
author: windows-driver-content
description: The VideoPortDoDma function is obsolete in Windows 2000 and later. VideoPortDoDma causes the miniport driver's HwVidStartDma function to be called.
old-location: display\videoportdodma.htm
old-project: display
ms.assetid: a827df55-ff88-439a-8d56-fba8212105a6
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , D, P, V, VideoPortDoDma, VideoPortDoDma function [Display Devices], VideoPort_Functions_febc78ee-355f-4689-9da9-f67f829d8a32.xml, a, d, display.videoportdodma, e, i, m, o, r, t, video/VideoPortDoDma"
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
-	VideoPortDoDma
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortDoDma function


## -description


The <b>VideoPortDoDma</b> function is <b>obsolete</b> in Windows 2000 and later. 

<b>VideoPortDoDma</b> causes the miniport driver's <i>HwVidStartDma</i> function to be called.


## -syntax


````
PDMA VideoPortDoDma(
  _In_ PVOID     HwDeviceExtension,
  _In_ PDMA      pDma,
  _In_ DMA_FLAGS DmaFlags
);
````


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param pDma [in]

Specifies a non-<b>NULL</b> DMA handle. This handle was obtained from a prior call to <b>VideoPortDoDma</b> or from the <b>OutputBuffer</b> member of the <a href="..\video\ns-video-_video_request_packet.md">VIDEO_REQUEST_PACKET</a> returned by <a href="..\video\nf-video-videoportlockpages.md">VideoPortLockPages</a>.


### -param DmaFlags [in]

Specifies the action to be performed. This member can be one of the following values:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>VideoPortKeepPagesLockedVideoPortDmaInitOnly</b>

</td>
<td>
If possible, the video port driver should keep the memory locked for subsequent DMA operation(s).

</td>
</tr>
<tr>
<td>
<b>VideoPortUnlockAfterDma</b>

</td>
<td>
The video port driver should unlock the memory after the DMA operation is performed.

</td>
</tr>
</table>
 


## -returns



<b>VideoPortDoDma</b> always returns <b>NULL</b>.




## -remarks



See <a href="https://msdn.microsoft.com/fe6c2e16-d222-4948-b1df-34ed8d57d9d8">Bus-Master DMA in Video Miniport Drivers</a> for information about packet-based and common-buffer DMA transfers.




## -see-also

<a href="..\video\ns-video-_video_request_packet.md">VIDEO_REQUEST_PACKET</a>



<a href="..\video\nf-video-videoportlockpages.md">VideoPortLockPages</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortDoDma function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

