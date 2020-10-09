---
UID: NC:video.PVIDEO_HW_LEGACYRESOURCES
title: PVIDEO_HW_LEGACYRESOURCES (video.h)
description: HwVidLegacyResources returns a list of resources that are not listed in a device's PCI configuration space but that are decoded by the device.
old-location: display\hwvidlegacyresources.htm
tech.root: display
ms.assetid: 015086e9-70b4-4756-9945-c9da17829e90
ms.date: 05/10/2018
keywords: ["PVIDEO_HW_LEGACYRESOURCES callback function"]
ms.keywords: HwVidLegacyResources, HwVidLegacyResources callback function [Display Devices], PVIDEO_HW_LEGACYRESOURCES, PVIDEO_HW_LEGACYRESOURCES callback, VideoMiniport_Functions_a629bf4d-8f16-4d71-ab88-c691160a5df7.xml, display.hwvidlegacyresources, video/HwVidLegacyResources
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
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
req.typenames: 
f1_keywords:
 - PVIDEO_HW_LEGACYRESOURCES
 - video/PVIDEO_HW_LEGACYRESOURCES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - video.h
api_name:
 - HwVidLegacyResources
---

# PVIDEO_HW_LEGACYRESOURCES callback function


## -description

<i>HwVidLegacyResources </i>returns a list of resources that are not listed in a device's PCI configuration space but that are decoded by the device.

## -parameters

### -param VendorId 

[in]
Specifies a code that identifies the device's vendor. This is the vendor ID specified in the device's PCI configuration space. For more information, see <a href="/windows-hardware/drivers/install/identifiers-for-pci-devices">Identifiers for PCI Devices</a>.

### -param DeviceId 

[in]
Specifies a code that identifies the particular device. This is the device ID specified in the device's PCI configuration space.

### -param LegacyResourceList 

[in, out]
Pointer to an array of <a href="/windows-hardware/drivers/ddi/video/ns-video-_video_access_range">VIDEO_ACCESS_RANGE</a> structures. Each structure describes a device I/O port or memory range for the graphics adapter that is not listed in PCI configuration space.

### -param LegacyResourceCount 

[in, out]
Is the number of elements in the array to which <i>LegacyResourceList</i> points.

## -remarks

Legacy resources are those resources that are not listed in the device's PCI configuration space but that are decoded by the device. If the legacy resource list for the device is not known at compile time, a miniport driver should implement a <i>HwVidLegacyResources </i> function and initialize the <b>HwGetLegacyResources</b> member of <a href="/windows-hardware/drivers/ddi/video/ns-video-_video_hw_initialization_data">VIDEO_HW_INITIALIZATION_DATA</a> to point to this function. For example, a miniport driver that supports two devices with different sets of legacy resources would implement <i>HwVidLegacyResources </i> to report the legacy resources for a particular device at run time.

The resources returned by <i>HwVidLegacyResources </i> are added to the list of resources that PnP reserves for the device.

<i>HwVidLegacyResources</i> should be made pageable.

## -see-also

<a href="/windows-hardware/drivers/ddi/video/ns-video-_video_hw_initialization_data">VIDEO_HW_INITIALIZATION_DATA</a>