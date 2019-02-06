---
UID: NS:video._VIDEO_PORT_INT10_INTERFACE
title: _VIDEO_PORT_INT10_INTERFACE (video.h)
description: The VIDEO_PORT_INT10_INTERFACE structure provides a way to allocate and deallocate memory in another thread's context, read from and write to that memory, and make INT10 BIOS calls.
old-location: display\video_port_int10_interface.htm
tech.root: display
ms.assetid: 551b2255-c221-4a95-a812-dec34f09438b
ms.date: 05/10/2018
ms.keywords: "*PVIDEO_PORT_INT10_INTERFACE, PVIDEO_PORT_INT10_INTERFACE, PVIDEO_PORT_INT10_INTERFACE structure pointer [Display Devices], VIDEO_PORT_INT10_INTERFACE, VIDEO_PORT_INT10_INTERFACE structure [Display Devices], Video_Structs_b0f9d9fa-c989-4989-9f63-deb0ca211144.xml, _VIDEO_PORT_INT10_INTERFACE, display.video_port_int10_interface, video/PVIDEO_PORT_INT10_INTERFACE, video/VIDEO_PORT_INT10_INTERFACE"
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
-	VIDEO_PORT_INT10_INTERFACE
product:
- Windows
targetos: Windows
req.typenames: VIDEO_PORT_INT10_INTERFACE, *PVIDEO_PORT_INT10_INTERFACE
---

# _VIDEO_PORT_INT10_INTERFACE structure


## -description


The VIDEO_PORT_INT10_INTERFACE structure provides a way to allocate and deallocate memory in another thread's context, read from and write to that memory, and make INT10 BIOS calls.


## -struct-fields




### -field Size

Specifies the size in bytes of this structure.


### -field Version

Specifies the version of the interface to be returned by the video port driver. The current interface version is defined in <i>video.h</i> and has the form VIDEO_PORT_INT10_INTERFACE_<i>N</i>.


### -field Context

Pointer to a video port driver-defined context for the interface.


### -field InterfaceReference

Pointer to the video port driver-implemented reference routine for this interface.


### -field InterfaceDereference

Pointer to the video port driver-implemented dereference routine for this interface.


### -field Int10AllocateBuffer

Pointer to the video port driver-implemented <a href="https://msdn.microsoft.com/2e6c8000-13e3-46fb-81be-18428fec2b21">Int10AllocateBuffer</a> routine.


### -field Int10FreeBuffer

Pointer to the video port driver-implemented <a href="https://msdn.microsoft.com/feb7dd98-8c44-405e-8e98-ffd6246cf0ee">Int10FreeBuffer</a> routine.


### -field Int10ReadMemory

Pointer to the video port driver-implemented <a href="https://msdn.microsoft.com/94b72ad0-1ace-4fde-a4a9-1078103e3d9b">Int10ReadMemory</a> routine.


### -field Int10WriteMemory

Pointer to the video port driver-implemented <a href="https://msdn.microsoft.com/a1143ca4-9c39-4bd7-92e1-473bdb447eb5">Int10WriteMemory</a> routine.


### -field Int10CallBios

Pointer to the video port driver-implemented <a href="https://msdn.microsoft.com/994a73bc-81a1-4d73-959c-cc89b242c073">Int10CallBios</a> routine.


## -remarks



PnP video miniport drivers that intend to make BIOS calls should fill in the <b>Size</b> and <b>Version</b> members of this structure, and then call <a href="https://msdn.microsoft.com/library/windows/hardware/ff570337">VideoPortQueryServices</a>, which initializes the remaining members of this structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff570337">VideoPortQueryServices</a>
 

 

