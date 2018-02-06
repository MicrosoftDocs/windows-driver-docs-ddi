---
UID: NS:video._VIDEO_PORT_INT10_INTERFACE
title: "_VIDEO_PORT_INT10_INTERFACE"
author: windows-driver-content
description: The VIDEO_PORT_INT10_INTERFACE structure provides a way to allocate and deallocate memory in another thread's context, read from and write to that memory, and make INT10 BIOS calls.
old-location: display\video_port_int10_interface.htm
old-project: display
ms.assetid: 551b2255-c221-4a95-a812-dec34f09438b
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: "*PVIDEO_PORT_INT10_INTERFACE, VIDEO_PORT_INT10_INTERFACE structure [Display Devices], PVIDEO_PORT_INT10_INTERFACE structure pointer [Display Devices], PVIDEO_PORT_INT10_INTERFACE, _VIDEO_PORT_INT10_INTERFACE, video/PVIDEO_PORT_INT10_INTERFACE, VIDEO_PORT_INT10_INTERFACE, Video_Structs_b0f9d9fa-c989-4989-9f63-deb0ca211144.xml, video/VIDEO_PORT_INT10_INTERFACE, display.video_port_int10_interface"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	video.h
apiname:
-	VIDEO_PORT_INT10_INTERFACE
product: Windows
targetos: Windows
req.typenames: "*PVIDEO_PORT_INT10_INTERFACE, VIDEO_PORT_INT10_INTERFACE"
req.product: Windows 10 or later.
---

# _VIDEO_PORT_INT10_INTERFACE structure


## -description


The VIDEO_PORT_INT10_INTERFACE structure provides a way to allocate and deallocate memory in another thread's context, read from and write to that memory, and make INT10 BIOS calls.


## -syntax


````
typedef struct _VIDEO_PORT_INT10_INTERFACE {
  USHORT                 Size;
  USHORT                 Version;
  PVOID                  Context;
  PINTERFACE_REFERENCE   InterfaceReference;
  PINTERFACE_DEREFERENCE InterfaceDereference;
  PINT10_ALLOCATE_BUFFER Int10AllocateBuffer;
  PINT10_FREE_BUFFER     Int10FreeBuffer;
  PINT10_READ_MEMORY     Int10ReadMemory;
  PINT10_WRITE_MEMORY    Int10WriteMemory;
  PINT10_CALL_BIOS       Int10CallBios;
} VIDEO_PORT_INT10_INTERFACE, *PVIDEO_PORT_INT10_INTERFACE;
````


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

Pointer to the video port driver-implemented <a href="..\video\nc-video-pint10_allocate_buffer.md">Int10AllocateBuffer</a> routine.


### -field Int10FreeBuffer

Pointer to the video port driver-implemented <a href="..\video\nc-video-pint10_free_buffer.md">Int10FreeBuffer</a> routine.


### -field Int10ReadMemory

Pointer to the video port driver-implemented <a href="..\video\nc-video-pint10_read_memory.md">Int10ReadMemory</a> routine.


### -field Int10WriteMemory

Pointer to the video port driver-implemented <a href="..\video\nc-video-pint10_write_memory.md">Int10WriteMemory</a> routine.


### -field Int10CallBios

Pointer to the video port driver-implemented <a href="..\video\nc-video-pint10_call_bios.md">Int10CallBios</a> routine.


## -remarks


PnP video miniport drivers that intend to make BIOS calls should fill in the <b>Size</b> and <b>Version</b> members of this structure, and then call <a href="..\video\nf-video-videoportqueryservices.md">VideoPortQueryServices</a>, which initializes the remaining members of this structure.



## -see-also

<a href="..\video\nf-video-videoportqueryservices.md">VideoPortQueryServices</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VIDEO_PORT_INT10_INTERFACE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

