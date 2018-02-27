---
UID: NS:video._VIDEO_PORT_AGP_INTERFACE
title: "_VIDEO_PORT_AGP_INTERFACE"
author: windows-driver-content
description: The VIDEO_PORT_AGP_INTERFACE structure describes the AGP service routines provided by the video port driver.
old-location: display\video_port_agp_interface.htm
old-project: display
ms.assetid: a2be4958-3f11-4b9d-9c0c-c339ebbbce04
ms.author: windowsdriverdev
ms.date: 2/24/2018
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	video.h
apiname:
-	VIDEO_PORT_AGP_INTERFACE
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_AGP_INTERFACE, *PVIDEO_PORT_AGP_INTERFACE
req.product: Windows 10 or later.
---

# _VIDEO_PORT_AGP_INTERFACE structure


## -description


The VIDEO_PORT_AGP_INTERFACE structure describes the AGP service routines provided by the video port driver.


## -syntax


````
typedef struct _VIDEO_PORT_AGP_INTERFACE {
  USHORT                 Size;
  USHORT                 Version;
  PVOID                  Context;
  PINTERFACE_REFERENCE   InterfaceReference;
  PINTERFACE_DEREFERENCE InterfaceDereference;
  PAGP_RESERVE_PHYSICAL  AgpReservePhysical;
  PAGP_RELEASE_PHYSICAL  AgpReleasePhysical;
  PAGP_COMMIT_PHYSICAL   AgpCommitPhysical;
  PAGP_FREE_PHYSICAL     AgpFreePhysical;
  PAGP_RESERVE_VIRTUAL   AgpReserveVirtual;
  PAGP_RELEASE_VIRTUAL   AgpReleaseVirtual;
  PAGP_COMMIT_VIRTUAL    AgpCommitVirtual;
  PAGP_FREE_VIRTUAL      AgpFreeVirtual;
  ULONGLONG              AgpAllocationLimit;
} VIDEO_PORT_AGP_INTERFACE, *PVIDEO_PORT_AGP_INTERFACE;
````


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

Pointer to the video port driver-implemented <a href="..\videoagp\nc-videoagp-pagp_reserve_physical.md">AgpReservePhysical</a> routine.


### -field AgpReleasePhysical

Pointer to the video port driver-implemented <a href="..\videoagp\nc-videoagp-pagp_release_physical.md">AgpReleasePhysical</a> routine.


### -field AgpCommitPhysical

Pointer to the video port driver-implemented <a href="..\videoagp\nc-videoagp-pagp_commit_physical.md">AgpCommitPhysical</a> routine.


### -field AgpFreePhysical

Pointer to the video port driver-implemented <a href="..\videoagp\nc-videoagp-pagp_free_physical.md">AgpFreePhysical</a> routine.


### -field AgpReserveVirtual

Pointer to the video port driver-implemented <a href="..\videoagp\nc-videoagp-pagp_reserve_virtual.md">AgpReserveVirtual</a> routine.


### -field AgpReleaseVirtual

Pointer to the video port driver-implemented <a href="..\videoagp\nc-videoagp-pagp_release_virtual.md">AgpReleaseVirtual</a> routine.


### -field AgpCommitVirtual

Pointer to the video port driver-implemented <a href="..\videoagp\nc-videoagp-pagp_commit_virtual.md">AgpCommitVirtual</a> routine.


### -field AgpFreeVirtual

Pointer to the video port driver-implemented <a href="..\videoagp\nc-videoagp-pagp_free_virtual.md">AgpFreeVirtual</a> routine.


### -field AgpAllocationLimit

Specifies the maximum total number of bytes of AGP memory that a miniport driver can commit.


## -remarks



PnP video miniport drivers that can use AGP must fill in the <b>Size</b> and <b>Version</b> members, and then call the <a href="..\video\nf-video-videoportqueryservices.md">VideoPortQueryServices</a> function, which initializes the remaining members of this structure.




## -see-also

<a href="..\video\nf-video-videoportqueryservices.md">VideoPortQueryServices</a>



<a href="..\wdm\ns-wdm-_interface.md">INTERFACE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VIDEO_PORT_AGP_INTERFACE structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

