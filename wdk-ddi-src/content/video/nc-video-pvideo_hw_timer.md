---
UID: NC:video.PVIDEO_HW_TIMER
title: PVIDEO_HW_TIMER
description: HwVidTimer is a video miniport driver routine called at timed intervals by the video port driver.
old-location: display\hwvidtimer.htm
tech.root: display
ms.assetid: bd41bbbf-4ec8-4e6c-8620-d8a9fe0b8bad
ms.date: 05/10/2018
ms.keywords: HwVidTimer, HwVidTimer callback function [Display Devices], PVIDEO_HW_TIMER, PVIDEO_HW_TIMER callback, VideoMiniport_Functions_80fa0df4-2b7c-4ffa-9048-e252b8af26cf.xml, display.hwvidtimer, video/HwVidTimer
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	video.h
api_name:
-	HwVidTimer
product:
- Windows
targetos: Windows
req.typenames: 
---

# PVIDEO_HW_TIMER callback function


## -description


<i>HwVidTimer</i> is a video miniport driver routine called at timed intervals by the video port driver.


## -parameters




### -param HwDeviceExtension

Pointer to the miniport driver's per-adapter storage area. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543119">Device Extensions</a>.


## -returns



None




## -remarks



<i>HwVidTimer</i> is an optional miniport driver function to which calls are enabled with <a href="https://msdn.microsoft.com/library/windows/hardware/ff570370">VideoPortStartTimer</a> and disabled with <a href="https://msdn.microsoft.com/library/windows/hardware/ff570371">VideoPortStopTimer</a>.

Any miniport driver can have a <i>HwVidTimer</i> function. For example, a <i>HwVidTimer</i> function could be used to read the state of the "VGA" registers on a high-end video adapter so that the miniport driver can emulate VGA-compatible behavior.

After a call to <b>VideoPortStartTimer</b>, the video port driver calls a miniport driver's <i>HwVidTimer</i> function at approximately one-second intervals until the miniport driver calls <b>VideoPortStopTimer</b>.

Note that the <i>HwVidTimer</i> function <i>must not</i> disable the timer with a call to <b>VideoPortStopTimer</b>.

<i>HwVidTimer</i> must not be made pageable.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff570370">VideoPortStartTimer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570371">VideoPortStopTimer</a>
 

 

