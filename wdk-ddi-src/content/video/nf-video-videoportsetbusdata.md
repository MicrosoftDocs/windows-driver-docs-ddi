---
UID: NF:video.VideoPortSetBusData
title: VideoPortSetBusData function (video.h)
description: The VideoPortSetBusData function sets bus-configuration data for an adapter on a dynamically configurable I/O bus with a published, standard interface.
old-location: display\videoportsetbusdata.htm
tech.root: display
ms.assetid: 2a9ce391-718e-4be0-9699-7612b63d31f0
ms.date: 05/10/2018
ms.keywords: VideoPortSetBusData, VideoPortSetBusData function [Display Devices], VideoPort_Functions_e7db4c76-eae1-4e06-9969-1e2b8fc71faf.xml, display.videoportsetbusdata, video/VideoPortSetBusData
ms.topic: function
f1_keywords:
 - "video/VideoPortSetBusData"
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Videoprt.sys
api_name:
- VideoPortSetBusData
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortSetBusData function


## -description


The <b>VideoPortSetBusData</b> function sets bus-configuration data for an adapter on a dynamically configurable I/O bus with a published, standard interface.


## -parameters




### -param HwDeviceExtension

Pointer to the miniport driver's device extension.


### -param BusDataType

Specifies the type of bus data to be set. Currently, its value can be one of <b>Cmos</b>, <b>EisaConfiguration</b>, or <b>PCIConfiguration</b>. However, additional types of standardized, dynamically configurable buses might be supported in the future. The upper bound on the bus types supported is always <b>MaximumBusDataType</b>.
      
     


### -param SlotNumber

For a <i>BusDataType</i> value of <b>Cmos</b>, specifies the location of the device on the bus. This parameter should be zero for all other bus types.


### -param Buffer [in]

Pointer to a caller-supplied storage area with configuration information specific to <i>BusDataType</i>.

When <b>PCIConfiguration</b> is specified, the buffer contains some or all of the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff537455(v=vs.85)">PCI_COMMON_CONFIG</a> information for the given <i>SlotNumber</i>. The specified <i>Offset</i> and <i>Length</i> determine how much information is supplied.


### -param Offset

Specifies the byte offset within the PCI_COMMON_CONFIG structure at which the caller-supplied configuration values begin. A miniport driver can use PCI_COMMON_HDR_LENGTH to specify the offset of the device-specific area in PCI_COMMON_CONFIG.


### -param Length

Specifies the number of bytes in <i>Buffer</i>.


## -returns



<b>VideoPortSetBusData</b> returns the number of bytes of data successfully set for the given <i>SlotNumber</i>. If the given <i>BusDataType</i> is not valid for the current platform or if the supplied information is invalid, <b>VideoPortSetBusData</b> returns zero.




## -remarks



Miniport drivers of adapters on a PCI bus seldom call <b>VideoPortSetBusData</b>, unless unusual circumstances or the nature of a particular driver's video adapter requires such a call.

For example, a miniport driver might call <b>VideoPortSetBusData</b> to clear a bit in the PCI status register if its adapter signals a target abort during initialization. If a PCI video adapter must be configured with device-specific data, its driver also calls this function. In either case, such a driver is then likely to call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nf-video-videoportgetaccessranges">VideoPortGetAccessRanges</a> with a <i>RequestedResources</i> pointer to a driver-supplied array of resource descriptors.

<b>VideoPortSetBusData</b> cannot be called from a miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nc-video-pvideo_hw_interrupt">HwVidInterrupt</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nc-video-pvideo_hw_timer">HwVidTimer</a> functions, or from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nf-video-videoportqueuedpc">VideoPortQueueDpc</a>, or from a callback to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nf-video-videoportsynchronizeexecution">VideoPortSynchronizeExecution</a>. 




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff546644(v=vs.85)">HalSetBusDataByOffset</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nc-video-pvideo_hw_find_adapter">HwVidFindAdapter</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff537455(v=vs.85)">PCI_COMMON_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_pci_slot_number">PCI_SLOT_NUMBER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nf-video-videoportgetaccessranges">VideoPortGetAccessRanges</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nf-video-videoportgetbusdata">VideoPortGetBusData</a>
 

 

