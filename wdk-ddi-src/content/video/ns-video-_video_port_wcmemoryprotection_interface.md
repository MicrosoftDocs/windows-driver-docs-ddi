---
UID: NS:video._VIDEO_PORT_WCMEMORYPROTECTION_INTERFACE
title: "_VIDEO_PORT_WCMEMORYPROTECTION_INTERFACE"
author: windows-driver-content
description: The VIDEO_PORT_WCMEMORYPROTECTION_INTERFACE structure describes the Write Combined video memory protection service routines implemented by the video port driver. The protected video memory cannot be accessed by the CPU.
old-location: display\video_port_wcmemoryprotection_interface.htm
old-project: display
ms.assetid: ac62a738-bde1-49e7-9c18-519471ec1092
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , *, *PVIDEO_PORT_WCMEMORYPROTECTION_INTERFACE, ,, A, C, D, E, F, I, M, N, O, P, PVIDEO_PORT_WCMEMORYPROTECTION_INTERFACE, PVIDEO_PORT_WCMEMORYPROTECTION_INTERFACE structure pointer [Display Devices], R, T, V, VIDEO_PORT_WCMEMORYPROTECTION_INTERFACE, VIDEO_PORT_WCMEMORYPROTECTION_INTERFACE structure [Display Devices], Video_Structs_15076908-e598-4025-8884-a9ed60b1668c.xml, W, Y, _, _VIDEO_PORT_WCMEMORYPROTECTION_INTERFACE, display.video_port_wcmemoryprotection_interface, video/PVIDEO_PORT_WCMEMORYPROTECTION_INTERFACE, video/VIDEO_PORT_WCMEMORYPROTECTION_INTERFACE"
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	video.h
apiname:
-	VIDEO_PORT_WCMEMORYPROTECTION_INTERFACE
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_WCMEMORYPROTECTION_INTERFACE, *PVIDEO_PORT_WCMEMORYPROTECTION_INTERFACE
req.product: Windows 10 or later.
---

# _VIDEO_PORT_WCMEMORYPROTECTION_INTERFACE structure


## -description


The VIDEO_PORT_WCMEMORYPROTECTION_INTERFACE structure describes the Write Combined video memory protection service routines implemented by the video port driver. The protected video memory cannot be accessed by the CPU.


## -syntax


````
typedef struct _VIDEO_PORT_WCMEMORYPROTECTION_INTERFACE {
  USHORT                 Size;
  USHORT                 Version;
  PVOID                  Context;
  PINTERFACE_REFERENCE   InterfaceReference;
  PINTERFACE_DEREFERENCE InterfaceDereference;
  PROTECT_WC_MEMORY      VideoPortProtectWCMemory;
  RESTORE_WC_MEMORY      VideoPortRestoreWCMemory;
} VIDEO_PORT_WCMEMORYPROTECTION_INTERFACE, *PVIDEO_PORT_WCMEMORYPROTECTION_INTERFACE;
````


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

Pointer to the video port driver's <a href="..\video\nc-video-protect_wc_memory.md">VideoPortProtectWCMemory</a> callback routine.


### -field VideoPortRestoreWCMemory

Pointer to the video port driver's <a href="..\video\nc-video-restore_wc_memory.md">VideoPortRestoreWCMemory</a> callback routine.


## -see-also

<a href="..\video\nc-video-restore_wc_memory.md">VideoPortRestoreWCMemory</a>



<a href="..\video\nc-video-protect_wc_memory.md">VideoPortProtectWCMemory</a>



<a href="..\video\nf-video-videoportqueryservices.md">VideoPortQueryServices</a>



<a href="..\wdm\ns-wdm-_interface.md">INTERFACE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VIDEO_PORT_WCMEMORYPROTECTION_INTERFACE structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

