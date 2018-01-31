---
UID: NF:video.VideoPortUnlockBuffer
title: VideoPortUnlockBuffer function
author: windows-driver-content
description: The VideoPortUnLockBuffer function unlocks physical pages described by the specified memory descriptor list (MDL).
old-location: display\videoportunlockbuffer.htm
old-project: display
ms.assetid: d5d34f32-026b-4c9f-86ae-a835d4e9c381
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: VideoPortUnlockBuffer function [Display Devices], video/VideoPortUnlockBuffer, VideoPortUnlockBuffer, VideoPort_Functions_2cb5a81f-1956-4431-bf54-7ee6e3d79eab.xml, display.videoportunlockbuffer
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Videoprt.sys
apiname:
-	VideoPortUnlockBuffer
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortUnlockBuffer function


## -description


The <b>VideoPortUnLockBuffer</b> function unlocks physical pages described by the specified memory descriptor list (<a href="https://msdn.microsoft.com/library/windows/hardware/ff554414">MDL</a>).


## -syntax


````
VOID VideoPortUnlockBuffer(
  _In_ PVOID HwDeviceExtension,
  _In_ PVOID Mdl
);
````


## -parameters




#### - HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


#### - Mdl [in]

Pointer to the MDL of the buffer to be released. This parameter should be the same pointer that was returned by <a href="..\video\nf-video-videoportlockbuffer.md">VideoPortLockBuffer</a>.


## -returns


None



## -see-also

<a href="..\video\nf-video-videoportlockbuffer.md">VideoPortLockBuffer</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortUnlockBuffer function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

