---
UID: NF:video.VideoPortMoveMemory
title: VideoPortMoveMemory function
author: windows-driver-content
description: The VideoPortMoveMemory function copies data from the source location to the destination location in system memory.
old-location: display\videoportmovememory.htm
old-project: display
ms.assetid: 32b754ef-2a85-4ba7-9d4f-3c2de2501319
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: video/VideoPortMoveMemory, VideoPortMoveMemory, VideoPortMoveMemory function [Display Devices], VideoPort_Functions_ab574585-85be-48ea-9713-25867812699a.xml, display.videoportmovememory
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
req.irql: See Remarks section.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Videoprt.sys
apiname:
-	VideoPortMoveMemory
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortMoveMemory function


## -description


The <b>VideoPortMoveMemory</b> function copies data from the source location to the destination location in system memory.


## -syntax


````
VOID VideoPortMoveMemory(
  _Inout_ PVOID Destination,
  _Inout_ PVOID Source,
          ULONG Length
);
````


## -parameters




### -param Destination [in, out]

Pointer to the destination location.


### -param Source [in, out]

Pointer to the location of the data to copy.


### -param Length

Specifies the number of bytes to copy.


## -returns



None




## -remarks



<b>VideoPortMoveMemory</b> moves memory either forward or backward, aligned or unaligned, in 4-byte blocks, followed by any remaining bytes.

The given <i>Destination</i> and <i>Source</i> must be in a mapped logical range returned by <b>VideoPortGetDeviceBase</b> and/or a <a href="https://msdn.microsoft.com/5f6fec1a-1134-4765-81be-9b50939e5e66">system space</a> RAM address, such as an address on the stack.

Callers of <b>VideoPortMoveMemory</b> can be running at any IRQL if both memory blocks are resident. Otherwise, the caller must be running at IRQL &lt; DISPATCH_LEVEL.




## -see-also

<a href="..\video\nf-video-videoportgetdevicebase.md">VideoPortGetDeviceBase</a>



<a href="..\video\nf-video-videoportzerodevicememory.md">VideoPortZeroDeviceMemory</a>



<a href="..\video\nf-video-videoportcomparememory.md">VideoPortCompareMemory</a>



<a href="..\video\nf-video-videoportzeromemory.md">VideoPortZeroMemory</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortMoveMemory function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

