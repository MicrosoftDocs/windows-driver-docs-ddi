---
UID: NS:video._VIDEO_PORT_AGP_INTERFACE
title: "_VIDEO_PORT_AGP_INTERFACE"
author: windows-driver-content
description: The VIDEO_PORT_AGP_INTERFACE structure describes the AGP service routines provided by the video port driver.
old-location: display\video_port_agp_interface.htm
old-project: display
ms.assetid: a2be4958-3f11-4b9d-9c0c-c339ebbbce04
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PVIDEO_PORT_AGP_INTERFACE, PVIDEO_PORT_AGP_INTERFACE, PVIDEO_PORT_AGP_INTERFACE structure pointer [Display Devices], VIDEO_PORT_AGP_INTERFACE, VIDEO_PORT_AGP_INTERFACE structure [Display Devices], Video_Structs_0b0b9383-1396-487e-afbb-5437ea3a2ec3.xml, _VIDEO_PORT_AGP_INTERFACE, display.video_port_agp_interface, video/PVIDEO_PORT_AGP_INTERFACE, video/VIDEO_PORT_AGP_INTERFACE"
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: See Remarks section.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	video.h
api_name:
-	VIDEO_PORT_AGP_INTERFACE
product:
- Windows
targetos: Windows
req.typenames: VIDEO_PORT_AGP_INTERFACE, *PVIDEO_PORT_AGP_INTERFACE
req.product: Windows 10 or later.
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

Pointer to the video port driver-implemented <a href="https://msdn.microsoft.com/b3e21c94-acd5-4767-8ba5-70b2dcfb2aaa">AgpReservePhysical</a> routine.


### -field AgpReleasePhysical

Pointer to the video port driver-implemented <a href="https://msdn.microsoft.com/4da0f5cb-a017-4df5-958b-c76b7a08495a">AgpReleasePhysical</a> routine.


### -field AgpCommitPhysical

Pointer to the video port driver-implemented <a href="https://msdn.microsoft.com/3c3a6936-7435-4a42-99e6-2c048613af23">AgpCommitPhysical</a> routine.


### -field AgpFreePhysical

Pointer to the video port driver-implemented <a href="https://msdn.microsoft.com/bb0e3330-5601-47dd-afc6-94a70b42daaf">AgpFreePhysical</a> routine.


### -field AgpReserveVirtual

Pointer to the video port driver-implemented <a href="https://msdn.microsoft.com/966dfc6c-6830-4872-b411-2801e3a4b753">AgpReserveVirtual</a> routine.


### -field AgpReleaseVirtual

Pointer to the video port driver-implemented <a href="https://msdn.microsoft.com/4e880b39-e0ee-4801-86b7-ffc06ed415ab">AgpReleaseVirtual</a> routine.


### -field AgpCommitVirtual

Pointer to the video port driver-implemented <a href="https://msdn.microsoft.com/8a3e7fcd-d838-47ad-a42b-7eb070f81418">AgpCommitVirtual</a> routine.


### -field AgpFreeVirtual

Pointer to the video port driver-implemented <a href="https://msdn.microsoft.com/a6f689ab-8cf1-4207-af2b-30957500c190">AgpFreeVirtual</a> routine.


### -field AgpAllocationLimit

Specifies the maximum total number of bytes of AGP memory that a miniport driver can commit.


## -remarks



PnP video miniport drivers that can use AGP must fill in the <b>Size</b> and <b>Version</b> members, and then call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570337">VideoPortQueryServices</a> function, which initializes the remaining members of this structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn895657">INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570337">VideoPortQueryServices</a>
 

 

