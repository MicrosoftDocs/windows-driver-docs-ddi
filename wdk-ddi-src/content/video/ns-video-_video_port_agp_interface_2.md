---
UID: NS:video._VIDEO_PORT_AGP_INTERFACE_2
title: _VIDEO_PORT_AGP_INTERFACE_2 (video.h)
description: The VIDEO_PORT_AGP_INTERFACE_2 structure describes the AGP service routines provided by the video port driver.
old-location: display\video_port_agp_interface_2.htm
tech.root: display
ms.assetid: 626cbf2d-2841-4b52-b17d-5377aa2f6264
ms.date: 05/10/2018
ms.keywords: "*PVIDEO_PORT_AGP_INTERFACE_2, PVIDEO_PORT_AGP_INTERFACE_2, PVIDEO_PORT_AGP_INTERFACE_2 structure pointer [Display Devices], VIDEO_PORT_AGP_INTERFACE_2, VIDEO_PORT_AGP_INTERFACE_2 structure [Display Devices], Video_Structs_99a2957c-7304-4e59-9609-748a5d7b878b.xml, _VIDEO_PORT_AGP_INTERFACE_2, display.video_port_agp_interface_2, video/PVIDEO_PORT_AGP_INTERFACE_2, video/VIDEO_PORT_AGP_INTERFACE_2"
ms.topic: struct
f1_keywords:
 - "video/VIDEO_PORT_AGP_INTERFACE_2"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- video.h
api_name:
- VIDEO_PORT_AGP_INTERFACE_2
product:
- Windows
targetos: Windows
req.typenames: VIDEO_PORT_AGP_INTERFACE_2, *PVIDEO_PORT_AGP_INTERFACE_2
---

# _VIDEO_PORT_AGP_INTERFACE_2 structure


## -description


The VIDEO_PORT_AGP_INTERFACE_2 structure describes the AGP service routines provided by the video port driver.


## -struct-fields




### -field Size

Specifies the size in bytes of this structure.


### -field Version

Specifies the version of the interface to be returned by the video port driver. The current interface version is defined in <i>video.h</i> and has the form VIDEO_PORT_AGP_INTERFACE_<i>N</i>.


### -field Context

Pointer to a video port driver-defined context for the interface.


### -field InterfaceReference

Pointer to the video port driver-implemented reference routine for this interface.


### -field InterfaceDereference

Pointer to the video port driver-implemented dereference routine for this interface.


### -field AgpReservePhysical

Pointer to the video port driver-implemented <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/videoagp/nc-videoagp-pagp_reserve_physical">AgpReservePhysical</a> routine.


### -field AgpReleasePhysical

Pointer to the video port driver-implemented <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/videoagp/nc-videoagp-pagp_release_physical">AgpReleasePhysical</a> routine.


### -field AgpCommitPhysical

Pointer to the video port driver-implemented <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/videoagp/nc-videoagp-pagp_commit_physical">AgpCommitPhysical</a> routine.


### -field AgpFreePhysical

Pointer to the video port driver-implemented <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/videoagp/nc-videoagp-pagp_free_physical">AgpFreePhysical</a> routine.


### -field AgpReserveVirtual

Pointer to the video port driver-implemented <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/videoagp/nc-videoagp-pagp_reserve_virtual">AgpReserveVirtual</a> routine.


### -field AgpReleaseVirtual

Pointer to the video port driver-implemented <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/videoagp/nc-videoagp-pagp_release_virtual">AgpReleaseVirtual</a> routine.


### -field AgpCommitVirtual

Pointer to the video port driver-implemented <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/videoagp/nc-videoagp-pagp_commit_virtual">AgpCommitVirtual</a> routine.


### -field AgpFreeVirtual

Pointer to the video port driver-implemented <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/videoagp/nc-videoagp-pagp_free_virtual">AgpFreeVirtual</a> routine.


### -field AgpAllocationLimit

Specifies the maximum total number of bytes of AGP memory that a miniport driver can commit.


### -field AgpSetRate

Pointer to the video port driver-implemented <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/videoagp/nc-videoagp-pagp_set_rate">AgpSetRate</a> routine.


## -remarks



PnP video miniport drivers that can use AGP must fill in the <b>Size</b> and <b>Version</b> members, and then call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportqueryservices">VideoPortQueryServices</a> function, which initializes the remaining members of this structure.

This structure is identical to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_port_agp_interface">VIDEO_PORT_AGP_INTERFACE</a> structure, except for the <b>AgpSetRate</b> member, which that structure lacks. Video miniport drivers should first attempt to use VIDEO_PORT_AGP_INTERFACE_2 in a call to <b>VideoPortQueryServices</b>. If that call fails, due to the fact that the AGP filter driver does not support the newer version of the AGP interface, the video miniport driver can make a second call to <b>VideoPortQueryServices</b>, this time passing a VIDEO_PORT_AGP_INTERFACE structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface">INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_port_agp_interface">VIDEO_PORT_AGP_INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportqueryservices">VideoPortQueryServices</a>
 

 

