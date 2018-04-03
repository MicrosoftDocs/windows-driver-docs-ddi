---
UID: NF:video.VideoPortSetBusData
title: VideoPortSetBusData function
author: windows-driver-content
description: The VideoPortSetBusData function sets bus-configuration data for an adapter on a dynamically configurable I/O bus with a published, standard interface.
old-location: display\videoportsetbusdata.htm
old-project: display
ms.assetid: 2a9ce391-718e-4be0-9699-7612b63d31f0
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: VideoPortSetBusData, VideoPortSetBusData function [Display Devices], VideoPort_Functions_e7db4c76-eae1-4e06-9969-1e2b8fc71faf.xml, display.videoportsetbusdata, video/VideoPortSetBusData
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
-	VideoPortSetBusData
product:
- Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
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

When <b>PCIConfiguration</b> is specified, the buffer contains some or all of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537455">PCI_COMMON_CONFIG</a> information for the given <i>SlotNumber</i>. The specified <i>Offset</i> and <i>Length</i> determine how much information is supplied.


### -param Offset

Specifies the byte offset within the PCI_COMMON_CONFIG structure at which the caller-supplied configuration values begin. A miniport driver can use PCI_COMMON_HDR_LENGTH to specify the offset of the device-specific area in PCI_COMMON_CONFIG.


### -param Length

Specifies the number of bytes in <i>Buffer</i>.


## -returns



<b>VideoPortSetBusData</b> returns the number of bytes of data successfully set for the given <i>SlotNumber</i>. If the given <i>BusDataType</i> is not valid for the current platform or if the supplied information is invalid, <b>VideoPortSetBusData</b> returns zero.




## -remarks



Miniport drivers of adapters on a PCI bus seldom call <b>VideoPortSetBusData</b>, unless unusual circumstances or the nature of a particular driver's video adapter requires such a call.

For example, a miniport driver might call <b>VideoPortSetBusData</b> to clear a bit in the PCI status register if its adapter signals a target abort during initialization. If a PCI video adapter must be configured with device-specific data, its driver also calls this function. In either case, such a driver is then likely to call <a href="https://msdn.microsoft.com/library/windows/hardware/ff570302">VideoPortGetAccessRanges</a> with a <i>RequestedResources</i> pointer to a driver-supplied array of resource descriptors.

<b>VideoPortSetBusData</b> cannot be called from a miniport driver's <a href="https://msdn.microsoft.com/523471e3-cf1e-48d2-b5f0-2f8d19ad71e0">HwVidInterrupt</a> or <a href="https://msdn.microsoft.com/bd41bbbf-4ec8-4e6c-8620-d8a9fe0b8bad">HwVidTimer</a> functions, or from <a href="https://msdn.microsoft.com/library/windows/hardware/ff570339">VideoPortQueueDpc</a>, or from a callback to <a href="https://msdn.microsoft.com/library/windows/hardware/ff570372">VideoPortSynchronizeExecution</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546633">HalSetBusDataByOffset</a>



<a href="https://msdn.microsoft.com/8c880eff-4b4c-439e-9239-f2343c1fe084">HwVidFindAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537455">PCI_COMMON_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558790">PCI_SLOT_NUMBER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570302">VideoPortGetAccessRanges</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570306">VideoPortGetBusData</a>
 

 

