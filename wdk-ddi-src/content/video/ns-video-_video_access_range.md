---
UID: NS:video._VIDEO_ACCESS_RANGE
title: "_VIDEO_ACCESS_RANGE"
author: windows-driver-content
description: The VIDEO_ACCESS_RANGE structure defines a device I/O port or memory range for the video adapter.
old-location: display\video_access_range.htm
old-project: display
ms.assetid: 200c957d-2ba4-488b-afd7-609c13543a7a
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: video/PVIDEO_ACCESS_RANGE, Video_Structs_b5c6bb55-a4a4-41be-879c-de6f71abe988.xml, video/VIDEO_ACCESS_RANGE, VIDEO_ACCESS_RANGE structure [Display Devices], VIDEO_ACCESS_RANGE, *PVIDEO_ACCESS_RANGE, display.video_access_range, _VIDEO_ACCESS_RANGE, PVIDEO_ACCESS_RANGE structure pointer [Display Devices], PVIDEO_ACCESS_RANGE
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
-	VIDEO_ACCESS_RANGE
product: Windows
targetos: Windows
req.typenames: "*PVIDEO_ACCESS_RANGE, VIDEO_ACCESS_RANGE"
req.product: Windows 10 or later.
---

# _VIDEO_ACCESS_RANGE structure


## -description


The VIDEO_ACCESS_RANGE structure defines a device I/O port or memory range for the video adapter. Every miniport driver's <a href="..\video\nc-video-pvideo_hw_find_adapter.md">HwVidFindAdapter</a> function must set up an array of VIDEO_ACCESS_RANGE-type elements, called the <i>access ranges array</i>, for each video adapter the miniport driver supports.

For VGA-compatible miniport drivers, VIDEO_ACCESS_RANGE also defines an element in an array passed to <a href="..\video\nf-video-videoportsettrappedemulatorports.md">VideoPortSetTrappedEmulatorPorts</a> to enable or disable direct access to I/O ports by full-screen MS-DOS applications.


## -syntax


````
typedef struct _VIDEO_ACCESS_RANGE {
  PHYSICAL_ADDRESS RangeStart;
  ULONG            RangeLength;
  UCHAR            RangeInIoSpace;
  UCHAR            RangeVisible;
  UCHAR            RangeShareable;
  UCHAR            RangePassive;
} VIDEO_ACCESS_RANGE, *PVIDEO_ACCESS_RANGE;
````


## -struct-fields




### -field RangeStart

Specifies the bus-relative base address of a memory or I/O port range for an element in the access ranges array passed to <a href="..\video\nf-video-videoportverifyaccessranges.md">VideoPortVerifyAccessRanges</a> or returned by <a href="..\video\nf-video-videoportgetaccessranges.md">VideoPortGetAccessRanges</a>.

Specifies the bus-relative base address of an I/O port range for an array to be passed to <a href="..\video\nf-video-videoportsettrappedemulatorports.md">VideoPortSetTrappedEmulatorPorts</a>.


### -field RangeLength

Specifies the number of I/O ports or size in bytes for the range.


### -field RangeInIoSpace

Specifies whether the range is in I/O space or in memory space. A value of <b>TRUE</b> (1) indicates that the range is in I/O space; a value of <b>FALSE</b> (0) indicates the range is in memory space.


### -field RangeVisible

Is ignored if the miniport driver's <a href="..\video\nc-video-pvideo_hw_find_adapter.md">HwVidFindAdapter</a> function is setting up the access ranges array.

Is set to <b>TRUE</b> by VGA-compatible miniport drivers and passed to <b>VideoPortSetTrappedEmulatorPorts</b> to enable direct access to the I/O port range by a full-screen MS-DOS application. If set to <b>FALSE</b>, application-issued instructions continue to be trapped and forwarded to the miniport driver's <i>SvgaHwIoXxx</i> function for validation.


### -field RangeShareable

Is set to <b>TRUE</b> if the access range described by this element can be shared with another driver and/or device or to <b>FALSE</b> if the range cannot be shared.

Is ignored by VideoPortSetTrappedEmulatorPorts.


### -field RangePassive

Indicates whether the device actually uses the port. Values for this member are shown in the following table.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
VIDEO_RANGE_PASSIVE_DECODE

</td>
<td>
The device decodes the port but the driver does not use it.

</td>
</tr>
<tr>
<td>
VIDEO_RANGE_10_BIT_DECODE

</td>
<td>
The device decodes ten bits of the port address.

</td>
</tr>
</table>
 


## -remarks



The miniport driver must claim legacy resources in its <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> or <a href="..\video\nc-video-pvideo_hw_legacyresources.md">HwVidLegacyResources</a> function.

Otherwise, a miniport driver's <a href="..\video\nc-video-pvideo_hw_find_adapter.md">HwVidFindAdapter</a> function sets up the access ranges array for an adapter's PCI resources. It can use information returned by <a href="..\video\nf-video-videoportgetaccessranges.md">VideoPortGetAccessRanges</a>. As an alternative, it can use information retrieved from the registry by calling <a href="..\video\nf-video-videoportgetdevicedata.md">VideoPortGetDeviceData</a> with a miniport driver-supplied <a href="..\video\nc-video-pminiport_query_device_routine.md">HwVidQueryDeviceCallback</a> function or <a href="..\video\nf-video-videoportgetregistryparameters.md">VideoPortGetRegistryParameters</a> with a miniport driver-supplied <a href="..\video\nc-video-pminiport_get_registry_routine.md">HwVidQueryNamedValueCallback</a> function. If calling these <b>VideoPort</b><i>Xxx</i> does not supply the bus-relative access range values, <i>HwVidFindAdapter</i> can set up access ranges elements using driver-supplied bus-relative default values.

<h3><a id="claiming_access_ranges_in_the_registry"></a><a id="CLAIMING_ACCESS_RANGES_IN_THE_REGISTRY"></a>Claiming Access Ranges in the Registry</h3>
The miniport driver should call <a href="..\video\nf-video-videoportverifyaccessranges.md">VideoPortVerifyAccessRanges</a> with any access ranges obtained from <b>VideoPortGetDeviceData</b>, <b>VideoPortGetAccessRanges</b>, or supplied as defaults by the miniport driver. If <b>VideoPortVerifyAccessRanges</b> returns NO_ERROR for such an array of access ranges, the <i>HwVidFindAdapter</i> or <i>HwVidQueryDeviceCallback</i> function can then map the ranges with <a href="..\video\nf-video-videoportgetdevicebase.md">VideoPortGetDeviceBase</a> and use the returned mapped logical addresses to access the adapter.

A successful call to <a href="..\video\nf-video-videoportgetaccessranges.md">VideoPortGetAccessRanges</a> also claims the returned bus-relative access ranges in the registry for the caller. If the miniport driver modifies any of the returned values, it must call <b>VideoPortVerifyAccessRanges</b> with the full access range, including any unmodified elements. Each call to <b>VideoPortGetAccessRanges</b> or <b>VideoPortVerifyAccessRanges</b> for a particular video adapter overwrites the caller's claimed hardware resources in the registry.

A miniport driver must not attempt to use a range for which <b>VideoPortVerifyAccessRanges</b> or <b>VideoPortGetAccessRanges</b> does not return NO_ERROR.

<h3><a id="mapping_access_ranges_to_communicate_with_the_adapter"></a><a id="MAPPING_ACCESS_RANGES_TO_COMMUNICATE_WITH_THE_ADAPTER"></a>Mapping Access Ranges to Communicate with the Adapter</h3>
After a miniport driver has claimed resources in the registry for an adapter, it cannot use bus-relative addresses to access or configure the adapter, because the HAL can remap all bus-relative device addresses to <a href="https://msdn.microsoft.com/5f6fec1a-1134-4765-81be-9b50939e5e66">system space</a>.

The miniport driver's <a href="..\video\nc-video-pvideo_hw_find_adapter.md">HwVidFindAdapter</a> function must call <a href="..\video\nf-video-videoportgetdevicebase.md">VideoPortGetDeviceBase</a> to get mapped logical addresses for its access ranges. Only then can the miniport driver communicate with the video adapter by passing the returned mapped logical range addresses to <b>VideoPortRead/WritePort</b><i>Xxx</i> to access device memory in I/O space and/or <b>VideoPortRead/WriteRegister</b><i>Xxx</i> to access device memory in memory space.

<h3><a id="determining_whether_an_access_range_is_shareable"></a><a id="DETERMINING_WHETHER_AN_ACCESS_RANGE_IS_SHAREABLE"></a>Determining whether an Access Range is Sharable</h3>
Follow these guidelines to determine whether an access range can be shared:

<ul>
<li>
If the range of memory or I/O ports should be "owned" by this driver, and/or access to this range by any other driver can cause a problem, set <b>RangeSharable</b> to <b>FALSE</b>.

</li>
<li>
If the range can be shared with a cooperating device driver, set <b>RangeSharable</b> to <b>TRUE</b>.

</li>
</ul>
SVGA miniport drivers that implement all VGA functionality (declared in the registry as <b>VgaCompatible</b> set to one) should claim their access ranges as unsharable so the system VGA driver will not be loaded. On the other hand, miniport drivers for adapters such as the S3 or the XGA, which set <b>VgaCompatible</b> to zero in the registry, should claim all the resources they share with the system VGA driver as sharable.

However, miniport drivers for cards that work with a pass-through IOCTL and that can be connected to any VGA or SVGA card should not be using any system VGA ports or memory ranges. If they do, such a driver should not attempt to claim any of the VGA access ranges in the registry. Attempts to claim VGA resources by such a miniport driver are likely to cause a resource conflict because the driver of any SVGA card in the machine will have claimed these access ranges as unsharable.

<h3><a id="passing_i_o_port_range_elements_to_videoportsettrappedemulatorports"></a><a id="PASSING_I_O_PORT_RANGE_ELEMENTS_TO_VIDEOPORTSETTRAPPEDEMULATORPORTS"></a>Passing I/O Port Range Elements to VideoPortSetTrappedEmulatorPorts</h3>
All VIDEO_ACCESS_RANGE-type array elements describing I/O port ranges are assumed to be invisible, unless a VGA-compatible miniport driver in an x86-based machine explicitly resets the <b>RangeVisible</b> member(s) to <b>TRUE</b> and calls <a href="..\video\nf-video-videoportsettrappedemulatorports.md">VideoPortSetTrappedEmulatorPorts</a> to enable one or more I/O port ranges. <b>VideoPortSetTrappedEmulatorPorts</b> ignores the <b>RangeSharable</b> members of the input array.

In an array of VIDEO_ACCESS_RANGE-type elements passed to <b>VideoPortSetTrappedEmulatorPorts</b>, the value of each element's <b>RangeVisible</b> member determines whether the given I/O port(s) can be accessed directly by the VDM (MS-DOS application running in full-screen on an x86-based machine) or whether such an application-issued I/O stream is trapped and forwarded to a miniport driver-supplied <i>SvgaHwIoPortXxx</i> function for validation first.




## -see-also

<a href="..\video\nc-video-pminiport_get_registry_routine.md">HwVidQueryNamedValueCallback</a>



<a href="..\video\nf-video-videoportgetaccessranges.md">VideoPortGetAccessRanges</a>



<a href="..\video\nf-video-videoportsettrappedemulatorports.md">VideoPortSetTrappedEmulatorPorts</a>



<a href="..\video\nf-video-videoportgetdevicedata.md">VideoPortGetDeviceData</a>



<a href="..\video\nf-video-videoportgetdevicebase.md">VideoPortGetDeviceBase</a>



<a href="..\video\nf-video-videoportgetregistryparameters.md">VideoPortGetRegistryParameters</a>



<a href="..\video\ns-video-_video_hw_initialization_data.md">VIDEO_HW_INITIALIZATION_DATA</a>



<a href="..\video\nc-video-pminiport_query_device_routine.md">HwVidQueryDeviceCallback</a>



<a href="..\video\nc-video-pvideo_hw_find_adapter.md">HwVidFindAdapter</a>



<a href="..\video\nf-video-videoportinitialize.md">VideoPortInitialize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556159">DriverEntry of Video Miniport Driver</a>



<a href="..\miniport\ns-miniport-_emulator_access_entry.md">EMULATOR_ACCESS_ENTRY</a>



<a href="..\video\nf-video-videoportverifyaccessranges.md">VideoPortVerifyAccessRanges</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VIDEO_ACCESS_RANGE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

