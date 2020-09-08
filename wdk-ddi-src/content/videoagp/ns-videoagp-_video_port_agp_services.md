---
UID: NS:videoagp._VIDEO_PORT_AGP_SERVICES
title: _VIDEO_PORT_AGP_SERVICES (videoagp.h)
description: The VIDEO_PORT_AGP_SERVICES structure is obsolete and is supported only for backward compatibility with existing drivers. In its place, driver writers should use VIDEO_PORT_AGP_INTERFACE.
old-location: display\video_port_agp_services.htm
tech.root: display
ms.assetid: 3e7d8f8e-a213-48ca-8a90-5d861271f6a2
ms.date: 05/10/2018
keywords: ["VIDEO_PORT_AGP_SERVICES structure"]
ms.keywords: "*PVIDEO_PORT_AGP_SERVICES, PVIDEO_PORT_AGP_SERVICES, PVIDEO_PORT_AGP_SERVICES structure pointer [Display Devices], VIDEO_PORT_AGP_SERVICES, VIDEO_PORT_AGP_SERVICES structure [Display Devices], Video_Structs_a667f879-7c09-4f48-9b23-920bb68a08cb.xml, _VIDEO_PORT_AGP_SERVICES, display.video_port_agp_services, videoagp/PVIDEO_PORT_AGP_SERVICES, videoagp/VIDEO_PORT_AGP_SERVICES"
req.header: videoagp.h
req.include-header: 
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
targetos: Windows
req.typenames: VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES
f1_keywords:
 - _VIDEO_PORT_AGP_SERVICES
 - videoagp/_VIDEO_PORT_AGP_SERVICES
 - PVIDEO_PORT_AGP_SERVICES
 - videoagp/PVIDEO_PORT_AGP_SERVICES
 - VIDEO_PORT_AGP_SERVICES
 - videoagp/VIDEO_PORT_AGP_SERVICES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - videoagp.h
api_name:
 - VIDEO_PORT_AGP_SERVICES
---

# _VIDEO_PORT_AGP_SERVICES structure


## -description

The VIDEO_PORT_AGP_SERVICES structure is <b>obsolete</b> and is supported only for backward compatibility with existing drivers. In its place, driver writers should use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_port_agp_interface">VIDEO_PORT_AGP_INTERFACE</a>.

The VIDEO_PORT_AGP_SERVICES structure describes the AGP service routines provided by the video port driver. PnP video miniport drivers that can use AGP should call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/videoagp/nf-videoagp-videoportgetagpservices">VideoPortGetAgpServices</a> to initialize this structure. The video port driver initializes the entire structure; the miniport driver should never change any members.

## -struct-fields

### -field AgpReservePhysical

### -field AgpReleasePhysical

### -field AgpCommitPhysical

### -field AgpFreePhysical

### -field AgpReserveVirtual

### -field AgpReleaseVirtual

### -field AgpCommitVirtual

### -field AgpFreeVirtual

### -field AllocationLimit

