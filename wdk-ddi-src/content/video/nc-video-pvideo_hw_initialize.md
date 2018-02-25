---
UID: NC:video.PVIDEO_HW_INITIALIZE
title: PVIDEO_HW_INITIALIZE
author: windows-driver-content
description: HwVidInitialize performs the first initialization of the adapter, after the HAL has given up control of the video hardware to the video port driver.
old-location: display\hwvidinitialize.htm
old-project: display
ms.assetid: 0e43de21-59e5-4368-8ea2-34fa52e99950
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: HwVidInitialize, HwVidInitialize callback function [Display Devices], PVIDEO_HW_INITIALIZE, VideoMiniport_Functions_7c9d848d-8129-45cc-91f0-7f66f536e7a6.xml, display.hwvidinitialize, video/HwVidInitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
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
-	UserDefined
apilocation:
-	video.h
apiname:
-	HwVidInitialize
product: Windows
targetos: Windows
req.typenames: VHF_CONFIG, *PVHF_CONFIG
req.product: Windows 10 or later.
---

# PVIDEO_HW_INITIALIZE callback


## -description


<i>HwVidInitialize</i> performs the first initialization of the adapter, after the HAL has given up control of the video hardware to the video port driver.


## -prototype


````
PVIDEO_HW_INITIALIZE HwVidInitialize;

BOOLEAN HwVidInitialize(
   PVOID HwDeviceExtension
)
{ ... }
````


## -parameters




### -param HwDeviceExtension

Pointer to the miniport driver's per-adapter storage area. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543119">Device Extensions</a>.


## -returns



If the initialization succeeds, <i>HwVidInitialize</i> returns <b>TRUE</b>.




## -remarks



Every video miniport driver must have a <i>HwVidInitialize</i> function.

The video port driver calls <i>HwVidInitialize</i> in response to an open request by the corresponding display driver. As soon as <i>HwVidInitialize</i> is called, the miniport driver can change the state of the adapter, unlike the miniport driver's <a href="..\video\nc-video-pvideo_hw_find_adapter.md">HwVidFindAdapter</a> function, which must leave the adapter in VGA mode. On return from <i>HwVidInitialize</i>, the adapter must be initialized to a state equivalent to that set up by the miniport driver's <a href="..\video\nc-video-pvideo_hw_reset_hw.md">HwVidResetHw</a> function. This feature is used by autodetection to get mode information from the miniport driver.

If at all possible, <i>HwVidInitialize</i> should avoid programming the device hardware. The miniport driver will initialize the device later, when it is instructed to switch display modes.

<i>HwVidInitialize</i> should be made pageable.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556178">DrvAssertMode</a>



<a href="..\video\nc-video-pvideo_hw_find_adapter.md">HwVidFindAdapter</a>



<a href="..\video\nc-video-pvideo_hw_reset_hw.md">HwVidResetHw</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PVIDEO_HW_INITIALIZE callback function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

