---
UID: NS:video._VIDEO_PORT_WCMEMORYPROTECTION_INTERFACE
title: _VIDEO_PORT_WCMEMORYPROTECTION_INTERFACE (video.h)
description: The VIDEO_PORT_WCMEMORYPROTECTION_INTERFACE structure describes the Write Combined video memory protection service routines implemented by the video port driver. The protected video memory cannot be accessed by the CPU.
old-location: display\video_port_wcmemoryprotection_interface.htm
tech.root: display
ms.assetid: ac62a738-bde1-49e7-9c18-519471ec1092
ms.date: 05/10/2018
keywords: ["VIDEO_PORT_WCMEMORYPROTECTION_INTERFACE structure"]
ms.keywords: "*PVIDEO_PORT_WCMEMORYPROTECTION_INTERFACE, PVIDEO_PORT_WCMEMORYPROTECTION_INTERFACE, PVIDEO_PORT_WCMEMORYPROTECTION_INTERFACE structure pointer [Display Devices], VIDEO_PORT_WCMEMORYPROTECTION_INTERFACE, VIDEO_PORT_WCMEMORYPROTECTION_INTERFACE structure [Display Devices], Video_Structs_15076908-e598-4025-8884-a9ed60b1668c.xml, _VIDEO_PORT_WCMEMORYPROTECTION_INTERFACE, display.video_port_wcmemoryprotection_interface, video/PVIDEO_PORT_WCMEMORYPROTECTION_INTERFACE, video/VIDEO_PORT_WCMEMORYPROTECTION_INTERFACE"
f1_keywords:
 - "video/VIDEO_PORT_WCMEMORYPROTECTION_INTERFACE"
 - "VIDEO_PORT_WCMEMORYPROTECTION_INTERFACE"
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
- VIDEO_PORT_WCMEMORYPROTECTION_INTERFACE
targetos: Windows
req.typenames: VIDEO_PORT_WCMEMORYPROTECTION_INTERFACE, *PVIDEO_PORT_WCMEMORYPROTECTION_INTERFACE
---

# _VIDEO_PORT_WCMEMORYPROTECTION_INTERFACE structure


## -description


The VIDEO_PORT_WCMEMORYPROTECTION_INTERFACE structure describes the Write Combined video memory protection service routines implemented by the video port driver. The protected video memory cannot be accessed by the CPU.


## -struct-fields




### -field Size

Specifies the size in bytes of this structure.


### -field Version

Specifies the version of the interface to be returned by the miniport driver. The current interface version is defined in <i>video.h</i>, and has the form VIDEO_PORT_WCMEMORYPROTECTION_INTERFACE_VERSION_<i>N</i>.


### -field Context

Pointer to a miniport driver-defined context for the interface.


### -field InterfaceReference

Pointer to the video port driver-implemented reference routine for this interface.


### -field InterfaceDereference

Pointer to the video port driver-implemented dereference routine for this interface.


### -field VideoPortProtectWCMemory

Pointer to the video port driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-protect_wc_memory">VideoPortProtectWCMemory</a> callback routine.


### -field VideoPortRestoreWCMemory

Pointer to the video port driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-restore_wc_memory">VideoPortRestoreWCMemory</a> callback routine.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface">INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-protect_wc_memory">VideoPortProtectWCMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportqueryservices">VideoPortQueryServices</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-restore_wc_memory">VideoPortRestoreWCMemory</a>
 

 

