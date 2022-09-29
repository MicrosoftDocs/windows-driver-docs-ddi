---
UID: NF:video.VideoPortGetAccessRanges
title: VideoPortGetAccessRanges function (video.h)
description: The VideoPortGetAccessRanges function retrieves bus-relative configuration information and, if possible, claims these hardware resources in the registry for the caller.
old-location: display\videoportgetaccessranges.htm
tech.root: display
ms.date: 08/18/2022
keywords: ["VideoPortGetAccessRanges function"]
ms.keywords: VideoPortGetAccessRanges, VideoPortGetAccessRanges function [Display Devices], VideoPort_Functions_a0db7d5d-01be-4c3c-9ea2-2ebd9b8aaca3.xml, display.videoportgetaccessranges, video/VideoPortGetAccessRanges
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 2000
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
targetos: Windows
req.typenames: 
f1_keywords:
 - VideoPortGetAccessRanges
 - video/VideoPortGetAccessRanges
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Videoprt.sys
api_name:
 - VideoPortGetAccessRanges
---

# VideoPortGetAccessRanges function

## -description

Deprecated. The **VideoPortGetAccessRanges** function retrieves bus-relative configuration information and, if possible, claims these hardware resources in the registry for the caller.

## -parameters

### -param HwDeviceExtension

Pointer to the miniport driver's device extension.

### -param NumRequestedResources

Specifies the number of elements in the **RequestedResources** array.

### -param RequestedResources

[in, optional] An array of IO_RESOURCE_DESCRIPTOR-type elements. Each descriptor specifies a single hardware resource that the miniport driver needs, prefers, or can use as an alternative to that specified in another array element. For detailed information about this structure, see the description of [**IoAssignResources**](/windows-hardware/drivers/kernel/mmcreatemdl).

### -param NumAccessRanges

Specifies the number of elements in the **AccessRanges** array.

### -param AccessRanges

[out] Pointer to an area on the stack or to a static structure in the miniport driver to which **VideoPortGetAccessRanges** returns an array of [**VIDEO_ACCESS_RANGE**](ns-video-_video_access_range.md) elements filled with the bus-relative device memory ranges for the adapter.

### -param VendorId

Should be set to NULL.

### -param DeviceId

Should be set to NULL.

### -param Slot

Pointer to a memory location in which the video port driver stores the slot number for the device, or is NULL.

For Plug and Play devices, if this is a valid pointer, the video port driver stores the slot number at the memory location specified by the pointer. If a NULL value is passed in the call, the video port driver does not store a value in the location.

## -returns

**VideoPortGetAccessRanges** returns NO_ERROR if it successfully filled in the **AccessRanges** information or returned configuration information at **RequestedResources**.

## -remarks

Every video miniport driver either must use access ranges returned by **VideoPortGetAccessRanges**, or must call [**VideoPortVerifyAccessRanges**](nf-video-videoportverifyaccessranges.md) before attempting to access a video adapter during the driver (and system) initialization process.

**VideoPortGetAccessRanges** can be called only from a miniport driver's [**HwVidFindAdapter**](nc-video-pvideo_hw_find_adapter.md) function.

For most miniport drivers, **VideoPortGetAccessRanges** can retrieve, verify, and claim the bus-relative access ranges and any interrupt and/or DMA channel/port used by a particular video adapter, while [**VideoPortVerifyAccessRanges**](nf-video-videoportverifyaccessranges.md) can only verify and claim miniport driver-specified resources. That is, for all configuration information that it returns, **VideoPortGetAccessRanges** claims the corresponding hardware resources in the registry for the caller. A miniport driver need not call **VideoPortVerifyAccessRanges** with the returned bus-relative configuration information, unless the miniport driver attempts to modify any of the returned values.

Each successful call to **VideoPortGetAccessRanges** or **VideoPortVerifyAccessRanges** for a particular adapter overwrites the miniport driver's preceding claim on hardware resources in the registry.

After a successful call to **VideoPortGetAccessRanges**, the miniport driver must map the returned bus-relative ranges to logical ranges with [**VideoPortGetDeviceBase**](nf-video-videoportgetdevicebase.md) *before* calling the appropriate **VideoPortRead/Write****Xxx** function to communicate with the adapter.

Generally, the miniport driver of a PCI device should have its [**HwVidFindAdapter**](nc-video-pvideo_hw_find_adapter.md) function call **VideoPortGetAccessRanges**, rather than attempt to manipulate the nondevice-specific PCI_COMMON_CONFIG information returned by a call to [**VideoPortGetBusData**](nf-video-videoportgetbusdata.md). This miniport driver can typically call **VideoPortGetAccessRanges** with a NULL**RequestedResources** pointer. The video port driver then uses the configuration space of the PCI bus to determine the resources for the video adapter. The miniport driver can call **VideoPortGetAccessRanges**, using a set of driver-supplied **RequestedResources** specifications, if its original call fails to return valid configuration data for the adapter.

Note that miniport drivers of adapters on other types of I/O buses also can call **VideoPortGetAccessRanges**. These drivers should call **VideoPortGetAccessRanges** using a **RequestedResources** pointer to a driver-supplied array of I/O resource descriptors.

If the **HwVidFindAdapter** function claims bus-relative access ranges and possibly other hardware resources for an adapter, but then determines that it does not support the adapter, then the miniport driver must relinquish its claims on hardware resources in the registry by calling **VideoPortGetAccessRanges** or **VideoPortVerifyAccessRanges** with the **NumAccessRanges** parameter set to zero.

## -see-also

[**HwVidFindAdapter**](nc-video-pvideo_hw_find_adapter.md)

[**IoAssignResources**](/windows-hardware/drivers/kernel/mmcreatemdl)

[**PCI_COMMON_CONFIG**](/previous-versions/windows/hardware/drivers/ff537455(v=vs.85))

[**PCI_SLOT_NUMBER**](../wdm/ns-wdm-_pci_slot_number.md)

[**VIDEO_PORT_CONFIG_INFO**](ns-video-_video_port_config_info.md)

[**VideoPortGetBusData**](nf-video-videoportgetbusdata.md)

[**VideoPortGetDeviceBase**](nf-video-videoportgetdevicebase.md)

[**VideoPortSetBusData**](nf-video-videoportsetbusdata.md)

[**VideoPortVerifyAccessRanges**](nf-video-videoportverifyaccessranges.md)
