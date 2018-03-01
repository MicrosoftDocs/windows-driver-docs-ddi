---
UID: NF:video.VideoPortGetAccessRanges
title: VideoPortGetAccessRanges function
author: windows-driver-content
description: The VideoPortGetAccessRanges function retrieves bus-relative configuration information and, if possible, claims these hardware resources in the registry for the caller.
old-location: display\videoportgetaccessranges.htm
old-project: display
ms.assetid: 7a858b32-408e-4926-9aba-44046b0266e2
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: VideoPortGetAccessRanges, VideoPortGetAccessRanges function [Display Devices], VideoPort_Functions_a0db7d5d-01be-4c3c-9ea2-2ebd9b8aaca3.xml, display.videoportgetaccessranges, video/VideoPortGetAccessRanges
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: video.h
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Videoprt.sys
api_name:
-	VideoPortGetAccessRanges
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortGetAccessRanges function


## -description


The <b>VideoPortGetAccessRanges</b> function retrieves bus-relative configuration information and, if possible, claims these hardware resources in the registry for the caller.


## -syntax


````
VP_STATUS VideoPortGetAccessRanges(
           PVOID                   HwDeviceExtension,
           ULONG                   NumRequestedResources,
  _In_opt_ PIO_RESOURCE_DESCRIPTOR RequestedResources,
           ULONG                   NumAccessRanges,
  _Out_    PVIDEO_ACCESS_RANGE     AccessRanges,
           PVOID                   VendorId,
           PVOID                   DeviceId,
           PULONG                  Slot
);
````


## -parameters




### -param HwDeviceExtension

Pointer to the miniport driver's device extension.


### -param NumRequestedResources

Specifies the number of elements in the <i>RequestedResources</i> array.


### -param OPTIONAL

TBD


### -param NumAccessRanges

Specifies the number of elements in the <i>AccessRanges</i> array.


### -param AccessRanges [out]

Pointer to an area on the stack or to a static structure in the miniport driver to which <b>VideoPortGetAccessRanges</b> returns an array of <a href="..\video\ns-video-_video_access_range.md">VIDEO_ACCESS_RANGE</a> elements filled with the bus-relative device memory ranges for the adapter.


### -param VendorId

Should be set to <b>NULL</b>.


### -param DeviceId

Should be set to <b>NULL</b>.


### -param Slot

Pointer to a memory location in which the video port driver stores the slot number for the device, or is <b>NULL</b>. 

For Plug and Play devices, if this is a valid pointer, the video port driver stores the slot number at the memory location specified by the pointer. If a <b>NULL</b> value is passed in the call, the video port driver does not store a value in the location.


#### - RequestedResources [in, optional]

An array of IO_RESOURCE_DESCRIPTOR-type elements. Each descriptor specifies a single hardware resource that the miniport driver needs, prefers, or can use as an alternative to that specified in another array element. For detailed information about this structure, see the description of <a href="https://msdn.microsoft.com/library/windows/hardware/ff548285">IoAssignResources</a>.


## -returns



<b>VideoPortGetAccessRanges</b> returns NO_ERROR if it successfully filled in the <i>AccessRanges</i> information or returned configuration information at <i>RequestedResources</i>.




## -remarks



Every video miniport driver either must use access ranges returned by <b>VideoPortGetAccessRanges</b>, or must call <a href="..\video\nf-video-videoportverifyaccessranges.md">VideoPortVerifyAccessRanges</a> before attempting to access a video adapter during the driver (and system) initialization process.

<b>VideoPortGetAccessRanges</b> can be called only from a miniport driver's <a href="..\video\nc-video-pvideo_hw_find_adapter.md">HwVidFindAdapter</a> function.

For most miniport drivers, <b>VideoPortGetAccessRanges</b> can retrieve, verify, and claim the bus-relative access ranges and any interrupt and/or DMA channel/port used by a particular video adapter, while <a href="..\video\nf-video-videoportverifyaccessranges.md">VideoPortVerifyAccessRanges</a> can only verify and claim miniport driver-specified resources. That is, for all configuration information that it returns, <b>VideoPortGetAccessRanges</b> claims the corresponding hardware resources in the registry for the caller. A miniport driver need not call <b>VideoPortVerifyAccessRanges</b> with the returned bus-relative configuration information, unless the miniport driver attempts to modify any of the returned values.

Each successful call to <b>VideoPortGetAccessRanges</b> or <b>VideoPortVerifyAccessRanges</b> for a particular adapter overwrites the miniport driver's preceding claim on hardware resources in the registry.

After a successful call to <b>VideoPortGetAccessRanges</b>, the miniport driver must map the returned bus-relative ranges to logical ranges with <a href="..\video\nf-video-videoportgetdevicebase.md">VideoPortGetDeviceBase </a><i>before</i> calling the appropriate <b>VideoPortRead/Write</b><i>Xxx</i> function to communicate with the adapter.

Generally, the miniport driver of a PCI device should have its <a href="..\video\nc-video-pvideo_hw_find_adapter.md">HwVidFindAdapter</a> function call <b>VideoPortGetAccessRanges</b>, rather than attempt to manipulate the nondevice-specific PCI_COMMON_CONFIG information returned by a call to <a href="..\video\nf-video-videoportgetbusdata.md">VideoPortGetBusData</a>. This miniport driver can typically call <b>VideoPortGetAccessRanges</b> with a <b>NULL</b><i>RequestedResources</i> pointer. The video port driver then uses the configuration space of the PCI bus to determine the resources for the video adapter. The miniport driver can call <b>VideoPortGetAccessRanges</b>, using a set of driver-supplied <i>RequestedResources</i> specifications, if its original call fails to return valid configuration data for the adapter.

Note that miniport drivers of adapters on other types of I/O buses also can call <b>VideoPortGetAccessRanges</b>. These drivers should call <b>VideoPortGetAccessRanges</b> using a <i>RequestedResources</i> pointer to a driver-supplied array of I/O resource descriptors.

If the <i>HwVidFindAdapter</i> function claims bus-relative access ranges and possibly other hardware resources for an adapter, but then determines that it does not support the adapter, then the miniport driver must relinquish its claims on hardware resources in the registry by calling <b>VideoPortGetAccessRanges</b> or <b>VideoPortVerifyAccessRanges</b> with the <i>NumAccessRanges</i> parameter set to zero.




## -see-also

<a href="..\video\ns-video-_video_port_config_info.md">VIDEO_PORT_CONFIG_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548285">IoAssignResources</a>



<a href="..\wdm\ns-wdm-_pci_common_config.md">PCI_COMMON_CONFIG</a>



<a href="..\video\nf-video-videoportgetdevicebase.md">VideoPortGetDeviceBase</a>



<a href="..\video\nc-video-pvideo_hw_find_adapter.md">HwVidFindAdapter</a>



<a href="..\video\nf-video-videoportgetbusdata.md">VideoPortGetBusData</a>



<a href="..\wdm\ns-wdm-_pci_slot_number.md">PCI_SLOT_NUMBER</a>



<a href="..\video\nf-video-videoportverifyaccessranges.md">VideoPortVerifyAccessRanges</a>



<a href="..\video\nf-video-videoportsetbusdata.md">VideoPortSetBusData</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortGetAccessRanges function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

