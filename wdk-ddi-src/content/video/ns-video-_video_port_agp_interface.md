---
UID: NS:video._VIDEO_PORT_AGP_INTERFACE
title: _VIDEO_PORT_AGP_INTERFACE (video.h)
description: The VIDEO_PORT_AGP_INTERFACE structure describes the AGP service routines provided by the video port driver.
old-location: display\video_port_agp_interface.htm
tech.root: display
ms.assetid: a2be4958-3f11-4b9d-9c0c-c339ebbbce04
ms.date: 05/10/2018
ms.keywords: "*PVIDEO_PORT_AGP_INTERFACE, PVIDEO_PORT_AGP_INTERFACE, PVIDEO_PORT_AGP_INTERFACE structure pointer [Display Devices], VIDEO_PORT_AGP_INTERFACE, VIDEO_PORT_AGP_INTERFACE structure [Display Devices], Video_Structs_0b0b9383-1396-487e-afbb-5437ea3a2ec3.xml, _VIDEO_PORT_AGP_INTERFACE, display.video_port_agp_interface, video/PVIDEO_PORT_AGP_INTERFACE, video/VIDEO_PORT_AGP_INTERFACE"
ms.topic: struct
f1_keywords:
 - "video/VIDEO_PORT_AGP_INTERFACE"
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
- VIDEO_PORT_AGP_INTERFACE
product:
- Windows
targetos: Windows
req.typenames: VIDEO_PORT_AGP_INTERFACE, *PVIDEO_PORT_AGP_INTERFACE
---

# _VIDEO_PORT_AGP_INTERFACE structure


## -description


The VIDEO_PORT_AGP_INTERFACE structure describes the AGP service routines provided by the video port driver.


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


## -remarks



PnP video miniport drivers that can use AGP must fill in the <b>Size</b> and <b>Version</b> members, and then call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportqueryservices">VideoPortQueryServices</a> function, which initializes the remaining members of this structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface">INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportqueryservices">VideoPortQueryServices</a>
 

 

