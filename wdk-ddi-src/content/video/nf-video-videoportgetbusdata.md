---
UID: NF:video.VideoPortGetBusData
title: VideoPortGetBusData function
author: windows-driver-content
description: The VideoPortGetBusData function returns bus-type-specific configuration information.
old-location: display\videoportgetbusdata.htm
tech.root: display
ms.assetid: ebc5e74f-82ba-4c19-8dae-3ebe8c843fd2
ms.date: 5/10/2018
ms.keywords: VideoPortGetBusData, VideoPortGetBusData function [Display Devices], VideoPort_Functions_98b5cc14-84db-4611-a651-652eb434cae6.xml, display.videoportgetbusdata, video/VideoPortGetBusData
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
-	VideoPortGetBusData
product:
- Windows
targetos: Windows
req.typenames: 
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


### -param Buffer [out]

Pointer to a buffer into which <b>VideoPortGetBusData</b> returns the configuration information. The contents of the buffer depend on the <i>BusDataType</i>, as follows:

<ul>
<li>
If <b>Cmos</b> is specified, the buffer contains the contents of the CMOS (bus number equals zero) or ECMOS (bus number equals one) locations, starting with the location specified for <i>SlotNumber</i>. A miniport driver's <a href="https://msdn.microsoft.com/8c880eff-4b4c-439e-9239-f2343c1fe084">HwVidFindAdapter</a> function can determine the number of the bus from the <b>SystemIoBusNumber</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570531">VIDEO_PORT_CONFIG_INFO</a> input structure.

</li>
<li>
If <b>EisaConfiguration</b> is specified, the buffer contains the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541941">CM_EISA_SLOT_INFORMATION</a> structure, followed by zero or more <a href="https://msdn.microsoft.com/library/windows/hardware/ff541930">CM_EISA_FUNCTION_INFORMATION</a> structures for the specified slot.

</li>
<li>
If <b>PCIConfiguration</b> is specified, the buffer contains the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537455">PCI_COMMON_CONFIG</a> information for the specified slot.

</li>
</ul>

### -param Offset

Specifies the offset, in bytes, into the PCI configuration space that should be retrieved If <i>BusDataType</i> is <b>PCIConfiguration</b>; otherwise zero. See <b>Remarks</b> for more information.


### -param Length

Specifies the length, in bytes, of <i>Buffer</i>.


## -returns



<b>VideoPortGetBusData</b> returns the number of bytes of configuration information it has written in <i>Buffer</i>. If the given <i>BusDataType</i> is not valid for the current platform, this function generally returns zero.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>0</b></dt>
</dl>
</td>
<td width="60%">
The PCI bus does not exist.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>2</b></dt>
</dl>
</td>
<td width="60%">
The PCI bus exists, but <i>Buffer</i> contains the value PCI_INVALID_VENDOR_ID at the PCI_COMMON_CONFIG <b>VendorId</b> member.

</td>
</tr>
</table>
 




## -remarks



To obtain only a part of the configuration information, the miniport driver should set <i>Offset</i> to the byte offset of the information needed, and set <i>Length</i> to the number of bytes of the information needed. For example, if only the command register is needed, set <i>Offset</i> to the offset of this register, and set <i>Length</i> to <b>sizeof</b>(USHORT).

The driver should call <a href="https://msdn.microsoft.com/library/windows/hardware/ff570302">VideoPortGetAccessRanges</a> rather than <b>VideoPortGetBusData</b> to retrieve its hardware resources. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541930">CM_EISA_FUNCTION_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541941">CM_EISA_SLOT_INFORMATION</a>



<a href="https://msdn.microsoft.com/81c3f484-427e-43b8-b7dd-12017533560b">HwVidQueryDeviceCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537455">PCI_COMMON_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558790">PCI_SLOT_NUMBER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570531">VIDEO_PORT_CONFIG_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570302">VideoPortGetAccessRanges</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570310">VideoPortGetDeviceBase</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570311">VideoPortGetDeviceData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570316">VideoPortGetRegistryParameters</a>
 

 

