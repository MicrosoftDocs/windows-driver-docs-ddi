---
UID: NF:videoagp.VideoPortGetAgpServices
title: VideoPortGetAgpServices function (videoagp.h)
description: The VideoPortGetAgpServices function is obsolete and is supported only for backward compatibility with existing drivers.
old-location: display\videoportgetagpservices.htm
tech.root: display
ms.assetid: 3b01831d-d429-4dc5-9b12-a0e1fc58634d
ms.date: 05/10/2018
keywords: ["VideoPortGetAgpServices function"]
ms.keywords: VideoPortGetAgpServices, VideoPortGetAgpServices function [Display Devices], VideoPort_Functions_498a8f06-f24e-4116-90df-30360fa111a1.xml, display.videoportgetagpservices, videoagp/VideoPortGetAgpServices
f1_keywords:
 - "videoagp/VideoPortGetAgpServices"
 - "VideoPortGetAgpServices"
req.header: videoagp.h
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Videoprt.sys
api_name:
- VideoPortGetAgpServices
targetos: Windows
req.typenames: 
---

# VideoPortGetAgpServices function


## -description


The <b>VideoPortGetAgpServices</b> function is <b>obsolete</b> and is supported only for backward compatibility with existing drivers. In its place, driver writers should use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportqueryservices">VideoPortQueryServices</a>.

<b>VideoPortGetAgpServices</b> returns a list of video port driver-implemented AGP service functions.


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param AgpServices [in]

Pointer to an uninitialized, miniport driver-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/videoagp/ns-videoagp-_video_port_agp_services">VIDEO_PORT_AGP_SERVICES</a> structure.


## -returns



<b>VideoPortGetAgpServices</b> returns <b>TRUE</b> after it successfully initializes the VIDEO_PORT_AGP_SERVICES structure to which <i>AgpServices</i> points; otherwise it returns <b>FALSE</b>.




## -remarks



PnP video miniport drivers that can use AGP should call <b>VideoPortGetAgpServices</b>.

The video port driver initializes the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/videoagp/ns-videoagp-_video_port_agp_services">VIDEO_PORT_AGP_SERVICES</a> structure as follows:

<ul>
<li>
All function pointers are initialized to point to the corresponding video port driver-implemented AGP service functions.

</li>
<li>
The <b>AllocationLimit</b> field is initialized to the maximum amount of AGP memory that a miniport driver is allowed to commit, in bytes.

</li>
</ul>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/videoagp/nc-videoagp-pagp_commit_physical">AgpCommitPhysical</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/videoagp/nc-videoagp-pagp_commit_virtual">AgpCommitVirtual</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/videoagp/nc-videoagp-pagp_free_physical">AgpFreePhysical</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/videoagp/nc-videoagp-pagp_free_virtual">AgpFreeVirtual</a>



<b>AgpReleasePhysical</b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/videoagp/nc-videoagp-pagp_release_virtual">AgpReleaseVirtual</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/videoagp/nc-videoagp-pagp_reserve_physical">AgpReservePhysical</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/videoagp/ns-videoagp-_video_port_agp_services">VIDEO_PORT_AGP_SERVICES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportqueryservices">VideoPortQueryServices</a>
 

 

