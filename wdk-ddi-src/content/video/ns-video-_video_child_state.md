---
UID: NS:video._VIDEO_CHILD_STATE
title: "_VIDEO_CHILD_STATE"
author: windows-driver-content
description: The VIDEO_CHILD_STATE structure contains information about a child device and the state into which it should be placed.
old-location: display\video_child_state.htm
tech.root: display
ms.assetid: 69a2eebb-9294-4fc1-871a-587792f84f35
ms.date: 5/10/2018
ms.keywords: "*PVIDEO_CHILD_STATE, PVIDEO_CHILD_STATE, PVIDEO_CHILD_STATE structure pointer [Display Devices], VIDEO_CHILD_STATE, VIDEO_CHILD_STATE structure [Display Devices], Video_Structs_330b2d6d-13da-4949-9827-73e7829931b6.xml, _VIDEO_CHILD_STATE, display.video_child_state, video/PVIDEO_CHILD_STATE, video/VIDEO_CHILD_STATE"
ms.topic: struct
req.header: video.h
req.include-header: Video.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	video.h
api_name:
-	VIDEO_CHILD_STATE
product:
- Windows
targetos: Windows
req.typenames: VIDEO_CHILD_STATE, *PVIDEO_CHILD_STATE
---

# _VIDEO_CHILD_STATE structure


## -description


The VIDEO_CHILD_STATE structure contains information about a child device and the state into which it should be placed.


## -struct-fields




### -field Id

Specifies the ID for a particular child device, as given to it by the miniport driver. This value is the same as that returned in the <i>UId</i> parameter of the <a href="https://msdn.microsoft.com/175030c1-95d9-4a3b-976c-16e04852cb91">HwVidGetVideoChildDescriptor</a> function.


### -field State

Specifies the new state, on or off, for the child device. A value of one (1) indicates that the child device should be turned on; a value of zero (0) indicates that it should be turned off. One possible use for <b>State</b> is in hotkey switching from one display device to another.


## -remarks



One member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570501">VIDEO_CHILD_STATE_CONFIGURATION</a> structure is an array of VIDEO_CHILD_STATE structures. Each of these structures maintains state information for one of an adapter's child devices.




## -see-also




<a href="https://msdn.microsoft.com/175030c1-95d9-4a3b-976c-16e04852cb91">HwVidGetVideoChildDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570501">VIDEO_CHILD_STATE_CONFIGURATION</a>
 

 

