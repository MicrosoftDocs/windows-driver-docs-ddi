---
UID: NF:video.VideoPortCreateSecondaryDisplay
title: VideoPortCreateSecondaryDisplay function
description: The VideoPortCreateSecondaryDisplay function enables dual-view support by creating a secondary device object for the given device.
old-location: display\videoportcreatesecondarydisplay.htm
tech.root: display
ms.assetid: 49dc9ed8-a506-475e-910f-5dce2ad9b168
ms.date: 05/10/2018
ms.keywords: VideoPortCreateSecondaryDisplay, VideoPortCreateSecondaryDisplay function [Display Devices], VideoPort_Functions_eda677fc-91b7-47d3-8407-615d5fbfcb3a.xml, display.videoportcreatesecondarydisplay, video/VideoPortCreateSecondaryDisplay
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Videoprt.sys
api_name:
-	VideoPortCreateSecondaryDisplay
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortCreateSecondaryDisplay function


## -description


The <b>VideoPortCreateSecondaryDisplay</b> function enables dual-view support by creating a secondary device object for the given device.


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension. This is the hardware extension for the device that wants to create additional display device objects.


### -param SecondaryDeviceExtension [in, out]

Pointer to the location in which to store the hardware device extension for the secondary display device.


### -param ulFlag [in]

Is a set of attributes for the secondary display device. This parameter is restricted to the following value:

|Value|Meaning|
|--- |--- |
|VIDEO_DUALVIEW_REMOVABLE|The secondary view can be removed.|
 
## -returns

<b>VideoPortCreateSecondaryDisplay</b> returns NO_ERROR if the secondary display device was successfully created. Otherwise, this function returns an error code. 




## -remarks



In Windows XP and later, a removable logical device will never become the <a href="https://msdn.microsoft.com/139a10e9-203b-499b-9291-8537eae9189c">primary display</a>.

Note that on some editions of Windows XP, <b>VideoPortCreateSecondaryDisplay</b> can deliberately fail to enable Dualview. In such cases, the display driver should remain in SingleView mode.

When the video minport driver calls <b>VideoPortCreateSecondaryDisplay</b>, the value of the <i>ulFlags</i> parameter must be equal to VIDEO_DUALVIEW_REMOVABLE, which is defined in <i>ntddvdeo.h</i>.

The flags VIDEO_DUALVIEW_PRIMARY and VIDEO_DUALVIEW_SECONDARY, which are defined in <i>ntddvdeo.h</i>, are for internal use only. The video miniport driver must never set these flags. 



