---
UID: NC:video.PVIDEO_HW_GET_CHILD_DESCRIPTOR
title: PVIDEO_HW_GET_CHILD_DESCRIPTOR
author: windows-driver-content
description: HwVidGetVideoChildDescriptor returns a descriptor, a type, and an identification number for a particular child device of the display adapter.
old-location: display\hwvidgetvideochilddescriptor.htm
old-project: display
ms.assetid: 175030c1-95d9-4a3b-976c-16e04852cb91
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: HwVidGetVideoChildDescriptor, HwVidGetVideoChildDescriptor callback function [Display Devices], PVIDEO_HW_GET_CHILD_DESCRIPTOR, VideoMiniport_Functions_15898023-8b0d-4cda-8970-4aeb0a7fc444.xml, display.hwvidgetvideochilddescriptor, video/HwVidGetVideoChildDescriptor
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	video.h
api_name:
-	HwVidGetVideoChildDescriptor
product:
- Windows
targetos: Windows
req.typenames: VHF_CONFIG, *PVHF_CONFIG
req.product: Windows 10 or later.
---

# PVIDEO_HW_GET_CHILD_DESCRIPTOR callback


## -description


<i>HwVidGetVideoChildDescriptor</i> returns a descriptor, a type, and an identification number for a particular child device of the display adapter.


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's per-adapter storage area. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543119">Device Extensions</a>.


### -param ChildEnumInfo [in]

Is a <a href="https://msdn.microsoft.com/library/windows/hardware/ff570499">VIDEO_CHILD_ENUM_INFO</a> structure that describes the device being enumerated.


### -param VideoChildType [out]

Pointer to a location in which the miniport driver returns the type of child being enumerated. This member can be one of the following from the VIDEO_CHILD_TYPE enumeration:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>Monitor</b>

</td>
<td>
The child device is a monitor.

If the miniport driver detects that the monitor has a DDC2-compliant <a href="https://msdn.microsoft.com/0dd010e7-3e10-422a-adcb-8fe7df9e29ab">EDID</a> structure associated with it, the miniport driver should extract the EDID information from the monitor and return it in the buffer to which <i>pChildDescriptor</i> points. The miniport driver can more easily obtain the EDID from the monitor by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff570290">VideoPortDDCMonitorHelper</a>.

If the detected monitor is not DDC2-compliant, the miniport driver should not return anything in <i>pChildDescriptor</i>.

</td>
</tr>
<tr>
<td>
<b>NonPrimaryChip</b>

</td>
<td>
Is reserved for system use.

</td>
</tr>
<tr>
<td>
<b>VideoChip</b>

</td>
<td>
The child device is the graphics chip.

The miniport driver should return this type when <i>ChildEnumInfo</i>.<b>ChildIndex</b> is DISPLAY_ADAPTER_HW_ID. The miniport driver should not return anything in <i>pChildDescriptor</i>.

</td>
</tr>
<tr>
<td>
<b>Other</b>

</td>
<td>
The child device has a separate device driver associated with it.

The miniport driver should return the device's PnP hardware identifier as a Unicode string in the buffer to which <i>pChildDescriptor</i> points. This string must match the <a href="https://msdn.microsoft.com/86688b5d-575d-42e1-9158-7ffba1aaf1d3">device ID</a> specified in the driver's INF file. It will be used by the operating system as the hardware ID for this device.

</td>
</tr>
</table>
 


### -param pChildDescriptor [out]

Pointer to a buffer in which the miniport driver can return data that identifies the device. The information returned depends on the child type specified in <i>VideoChildType</i>. The size of this buffer is specified by the video port driver in the <b>ChildDescriptorSize</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff570499">VIDEO_CHILD_ENUM_INFO</a>.


### -param UId [out]

Pointer to the location in which the miniport driver returns a unique 32-bit <a href="https://msdn.microsoft.com/86688b5d-575d-42e1-9158-7ffba1aaf1d3">device ID</a> for this device. The miniport driver should set <i>UId</i> to be DISPLAY_ADAPTER_HW_ID when the device is the actual display adapter.


### -param pUnused [out]

Is unused and must be set to zero.


## -returns



<i>HwVidGetVideoChildDescriptor</i> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>VIDEO_ENUM_INVALID_DEVICE</b></dt>
</dl>
</td>
<td width="60%">
Call again. The miniport driver could not enumerate the child device identified in <i>ChildEnumInfo</i> but there are more devices to be enumerated. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>VIDEO_ENUM_MORE_DEVICES</b></dt>
</dl>
</td>
<td width="60%">
A new child device is enumerated. The video port will call <i>HwVidGetVideoChildDescriptor</i> again in this case.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>VIDEO_ENUM_NO_MORE_DEVICES</b></dt>
</dl>
</td>
<td width="60%">
The miniport driver could not enumerate the child device identified in <i>ChildEnumInfo</i>. Stop enumeration. There are no more devices to be enumerated. 

</td>
</tr>
</table>
 




## -remarks



By default, <i>HwVidGetVideoChildDescriptor</i> is not called until after the device is started by <a href="https://msdn.microsoft.com/8c880eff-4b4c-439e-9239-f2343c1fe084">HwVidFindAdapter</a>. To allow the enumeration of a device's children before the device is started, set the <b>AllowEarlyEnumeration</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff570505">VIDEO_HW_INITIALIZATION_DATA</a>. When <b>AllowEarlyEnumeration</b> is set, <i>HwVidGetVideoChildDescriptor</i> can be called at any time.

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




<a href="https://msdn.microsoft.com/747cfbfb-2a38-4a0d-b8c6-662d0c3967ba">HwVidGetPowerState</a>



<a href="https://msdn.microsoft.com/d7800ab6-9d8f-47a7-b919-8b6b0197d163">HwVidSetPowerState</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570499">VIDEO_CHILD_ENUM_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570290">VideoPortDDCMonitorHelper</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570297">VideoPortEnumerateChildren</a>
 

 

