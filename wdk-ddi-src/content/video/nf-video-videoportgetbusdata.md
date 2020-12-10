---
UID: NF:video.VideoPortGetBusData
title: VideoPortGetBusData function (video.h)
description: The VideoPortGetBusData function returns bus-type-specific configuration information.
old-location: display\videoportgetbusdata.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["VideoPortGetBusData function"]
ms.keywords: VideoPortGetBusData, VideoPortGetBusData function [Display Devices], VideoPort_Functions_98b5cc14-84db-4611-a651-652eb434cae6.xml, display.videoportgetbusdata, video/VideoPortGetBusData
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
targetos: Windows
req.typenames: 
f1_keywords:
 - VideoPortGetBusData
 - video/VideoPortGetBusData
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Videoprt.sys
api_name:
 - VideoPortGetBusData
---

# VideoPortGetBusData function


## -description

The <b>VideoPortGetBusData</b> function returns bus-type-specific configuration information.

## -parameters

### -param HwDeviceExtension

Pointer to the miniport driver's device extension.

### -param BusDataType

Specifies the type of bus configuration data to return. The value of this parameter can be <b>Cmos</b>, <b>EisaConfiguration</b>, or <b>PCIConfiguration</b>. However, additional types of bus configuration might be supported in the future. The upper bound on the types supported is always <b>MaximumBusDataType</b>.

### -param SlotNumber

Specifies the location of the device on the bus for a <b>Cmos </b><i>BusDataType</i>; zero for all other bus types.

### -param Buffer 

[out]
Pointer to a buffer into which <b>VideoPortGetBusData</b> returns the configuration information. The contents of the buffer depend on the <i>BusDataType</i>, as follows:

<ul>
<li>
If <b>Cmos</b> is specified, the buffer contains the contents of the CMOS (bus number equals zero) or ECMOS (bus number equals one) locations, starting with the location specified for <i>SlotNumber</i>. A miniport driver's <a href="/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_find_adapter">HwVidFindAdapter</a> function can determine the number of the bus from the <b>SystemIoBusNumber</b> member of the <a href="/windows-hardware/drivers/ddi/video/ns-video-_video_port_config_info">VIDEO_PORT_CONFIG_INFO</a> input structure.

</li>
<li>
If <b>EisaConfiguration</b> is specified, the buffer contains the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_eisa_slot_information">CM_EISA_SLOT_INFORMATION</a> structure, followed by zero or more <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_eisa_function_information">CM_EISA_FUNCTION_INFORMATION</a> structures for the specified slot.

</li>
<li>
If <b>PCIConfiguration</b> is specified, the buffer contains the <a href="/previous-versions/windows/hardware/drivers/ff537455(v=vs.85)">PCI_COMMON_CONFIG</a> information for the specified slot.

</li>
</ul>

### -param Offset

Specifies the offset, in bytes, into the PCI configuration space that should be retrieved If <i>BusDataType</i> is <b>PCIConfiguration</b>; otherwise zero. See <b>Remarks</b> for more information.

### -param Length

Specifies the length, in bytes, of <i>Buffer</i>.

## -returns

<b>VideoPortGetBusData</b> returns the number of bytes of configuration information it has written in <i>Buffer</i>. If the given <i>BusDataType</i> is not valid for the current platform, this function generally returns zero.

|Return code|Description|
|--- |--- |
|0|The PCI bus does not exist.|
|2|The PCI bus exists, but Buffer contains the value PCI_INVALID_VENDOR_ID at the PCI_COMMON_CONFIG VendorId member.|

## -remarks

To obtain only a part of the configuration information, the miniport driver should set <i>Offset</i> to the byte offset of the information needed, and set <i>Length</i> to the number of bytes of the information needed. For example, if only the command register is needed, set <i>Offset</i> to the offset of this register, and set <i>Length</i> to <b>sizeof</b>(USHORT).

The driver should call <a href="/windows-hardware/drivers/ddi/video/nf-video-videoportgetaccessranges">VideoPortGetAccessRanges</a> rather than <b>VideoPortGetBusData</b> to retrieve its hardware resources.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_eisa_function_information">CM_EISA_FUNCTION_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_eisa_slot_information">CM_EISA_SLOT_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/video/nc-video-pminiport_query_device_routine">HwVidQueryDeviceCallback</a>



<a href="/previous-versions/windows/hardware/drivers/ff537455(v=vs.85)">PCI_COMMON_CONFIG</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_pci_slot_number">PCI_SLOT_NUMBER</a>



<a href="/windows-hardware/drivers/ddi/video/ns-video-_video_port_config_info">VIDEO_PORT_CONFIG_INFO</a>



<a href="/windows-hardware/drivers/ddi/video/nf-video-videoportgetaccessranges">VideoPortGetAccessRanges</a>



<a href="/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>



<a href="/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicedata">VideoPortGetDeviceData</a>



<a href="/windows-hardware/drivers/ddi/video/nf-video-videoportgetregistryparameters">VideoPortGetRegistryParameters</a>
