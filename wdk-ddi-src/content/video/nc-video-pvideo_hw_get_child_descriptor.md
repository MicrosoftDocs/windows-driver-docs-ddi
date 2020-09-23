---
UID: NC:video.PVIDEO_HW_GET_CHILD_DESCRIPTOR
title: PVIDEO_HW_GET_CHILD_DESCRIPTOR (video.h)
description: HwVidGetVideoChildDescriptor returns a descriptor, a type, and an identification number for a particular child device of the display adapter.
old-location: display\hwvidgetvideochilddescriptor.htm
tech.root: display
ms.assetid: 175030c1-95d9-4a3b-976c-16e04852cb91
ms.date: 05/10/2018
keywords: ["PVIDEO_HW_GET_CHILD_DESCRIPTOR callback function"]
ms.keywords: HwVidGetVideoChildDescriptor, HwVidGetVideoChildDescriptor callback function [Display Devices], PVIDEO_HW_GET_CHILD_DESCRIPTOR, PVIDEO_HW_GET_CHILD_DESCRIPTOR callback, VideoMiniport_Functions_15898023-8b0d-4cda-8970-4aeb0a7fc444.xml, display.hwvidgetvideochilddescriptor, video/HwVidGetVideoChildDescriptor
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
 - PVIDEO_HW_GET_CHILD_DESCRIPTOR
 - video/PVIDEO_HW_GET_CHILD_DESCRIPTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - video.h
api_name:
 - HwVidGetVideoChildDescriptor
---

# PVIDEO_HW_GET_CHILD_DESCRIPTOR callback function


## -description

<i>HwVidGetVideoChildDescriptor</i> returns a descriptor, a type, and an identification number for a particular child device of the display adapter.

## -parameters

### -param HwDeviceExtension 

[in]
Pointer to the miniport driver's per-adapter storage area. For more information, see <a href="/windows-hardware/drivers/kernel/device-extensions">Device Extensions</a>.

### -param ChildEnumInfo 

[in]
Is a <a href="/windows-hardware/drivers/ddi/video/ns-video-_video_child_enum_info">VIDEO_CHILD_ENUM_INFO</a> structure that describes the device being enumerated.

### -param VideoChildType 

[out]
Pointer to a location in which the miniport driver returns the type of child being enumerated. This member can be one of the following from the VIDEO_CHILD_TYPE enumeration:

| **Value** | **Meaning** |
|:--|:--|
| **Monitor** | The child device is a monitor. If the miniport driver detects that the monitor has a DDC2-compliant [EDID](/windows-hardware/drivers/)  structure associated with it, the miniport driver should extract the EDID information from the monitor and return it in the buffer to which pChildDescriptor points. The miniport driver can more easily obtain the EDID from the monitor by calling [VideoPortDDCMonitorHelper](./nf-video-videoportddcmonitorhelper.md). <br/>If the detected monitor is not DDC2-compliant, the miniport driver should not return anything in pChildDescriptor. |
| **NonPrimaryChip** | Is reserved for system use. |
| **VideoChip** | The child device is the graphics chip.<br/>The miniport driver should return this type when ChildEnumInfo.ChildIndex is DISPLAY_ADAPTER_HW_ID. The miniport driver should not return anything in pChildDescriptor. | 
| **Other** | The child device has a separate device driver associated with it.<br/>The miniport driver should return the device's PnP hardware identifier as a Unicode string in the buffer to which pChildDescriptor points. This string must match the [device ID](/windows-hardware/drivers/)  specified in the driver's INF file. It will be used by the operating system as the hardware ID for this device. |

### -param pChildDescriptor 

[out]
Pointer to a buffer in which the miniport driver can return data that identifies the device. The information returned depends on the child type specified in <i>VideoChildType</i>. The size of this buffer is specified by the video port driver in the <b>ChildDescriptorSize</b> member of <a href="/windows-hardware/drivers/ddi/video/ns-video-_video_child_enum_info">VIDEO_CHILD_ENUM_INFO</a>.

### -param UId 

[out]
Pointer to the location in which the miniport driver returns a unique 32-bit <a href="/windows-hardware/drivers/">device ID</a> for this device. The miniport driver should set <i>UId</i> to be DISPLAY_ADAPTER_HW_ID when the device is the actual display adapter.

### -param pUnused 

[out]
Is unused and must be set to zero.

## -returns

<i>HwVidGetVideoChildDescriptor</i> returns one of the following values:

|Return code|Description|
|--- |--- |
|VIDEO_ENUM_INVALID_DEVICE|Call again. The miniport driver could not enumerate the child device identified in ChildEnumInfo but there are more devices to be enumerated.|
|VIDEO_ENUM_MORE_DEVICES|A new child device is enumerated. The video port will call HwVidGetVideoChildDescriptor again in this case.|
|VIDEO_ENUM_NO_MORE_DEVICES|The miniport driver could not enumerate the child device identified in ChildEnumInfo. Stop enumeration. There are no more devices to be enumerated.|

## -remarks

By default, <i>HwVidGetVideoChildDescriptor</i> is not called until after the device is started by <a href="/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_find_adapter">HwVidFindAdapter</a>. To allow the enumeration of a device's children before the device is started, set the <b>AllowEarlyEnumeration</b> member of <a href="/windows-hardware/drivers/ddi/video/ns-video-_video_hw_initialization_data">VIDEO_HW_INITIALIZATION_DATA</a>. When <b>AllowEarlyEnumeration</b> is set, <i>HwVidGetVideoChildDescriptor</i> can be called at any time.

<i>HwVidGetVideoChildDescriptor</i> should do the following:

<ul>
<li>
Determine the type of the child device based on the data supplied in <i>ChildEnumInfo</i>, and return this type in <i>VideoChildType</i>.

</li>
<li>
Fill in the buffer to which <i>pChildDescriptor</i> points with the appropriate data, depending on the value of <i>VideoChildType</i>.

</li>
<li>
Write a 32-bit value in <i>UId</i> that uniquely identifies the child device being enumerated. The video port driver will pass this handle back to the miniport driver for operations such as power management.

</li>
</ul>
<i>HwVidGetVideoChildDescriptor</i> should be made pageable.

## -see-also

<a href="/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_power_get">HwVidGetPowerState</a>



<a href="/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_power_set">HwVidSetPowerState</a>



<a href="/windows-hardware/drivers/ddi/video/ns-video-_video_child_enum_info">VIDEO_CHILD_ENUM_INFO</a>



<a href="/windows-hardware/drivers/ddi/video/nf-video-videoportddcmonitorhelper">VideoPortDDCMonitorHelper</a>



<a href="/windows-hardware/drivers/ddi/video/nf-video-videoportenumeratechildren">VideoPortEnumerateChildren</a>