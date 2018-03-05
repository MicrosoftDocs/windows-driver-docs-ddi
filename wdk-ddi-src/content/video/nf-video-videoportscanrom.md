---
UID: NF:video.VideoPortScanRom
title: VideoPortScanRom function
author: windows-driver-content
description: The VideoPortScanRom function is obsolete in Windows XP and later versions. It is supported only for backward compatibility. VideoPortScanRom performs a case-sensitive search for a specified string in ROM.
old-location: display\videoportscanrom.htm
old-project: display
ms.assetid: 7787237c-5afd-46f2-ac75-6c0b41d37352
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: VideoPortScanRom, VideoPortScanRom function [Display Devices], VideoPort_Functions_7bcf750d-48d5-4b3b-911f-90efd1f0eed1.xml, display.videoportscanrom, video/VideoPortScanRom
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Videoprt.sys
api_name:
-	VideoPortScanRom
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortScanRom function


## -description


The <b>VideoPortScanRom</b> function is <b>obsolete</b> in Windows XP and later versions. It is supported only for backward compatibility. 

<b>VideoPortScanRom</b> performs a case-sensitive search for a specified string in ROM.


## -syntax


````
BOOLEAN VideoPortScanRom(
   PVOID  HwDeviceExtension,
   PUCHAR RomBase,
   ULONG  RomLength,
   PUCHAR String
);
````


## -parameters




### -param HwDeviceExtension

Pointer to the miniport driver's device extension.


### -param RomBase

Specifies the base ROM address at which the search should start. The given <i>RomBase</i> must be in a mapped range returned by <a href="..\video\nf-video-videoportgetdevicebase.md">VideoPortGetDeviceBase</a>.


### -param RomLength

Specifies the size in bytes of the mapped ROM to be searched.


### -param String

Pointer to the driver-allocated string to search for.


## -returns



If the string is found, <b>VideoPortScanRom</b> returns <b>TRUE</b>. Otherwise, it returns <b>FALSE</b>.




## -remarks



<b>VideoPortScanRom</b> cannot be called from a miniport driver's <a href="..\video\nc-video-pvideo_hw_interrupt.md">HwVidInterrupt</a> or <a href="..\video\nc-video-pvideo_hw_timer.md">HwVidTimer</a> functions, or from <a href="..\video\nf-video-videoportqueuedpc.md">VideoPortQueueDpc</a>, or from a callback to <a href="..\video\nf-video-videoportsynchronizeexecution.md">VideoPortSynchronizeExecution</a>. 




## -see-also

<a href="..\video\nf-video-videoportgetromimage.md">VideoPortGetRomImage</a>



<a href="..\video\nf-video-videoportgetdevicebase.md">VideoPortGetDeviceBase</a>



<a href="..\video\nc-video-pvideo_hw_find_adapter.md">HwVidFindAdapter</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortScanRom function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

