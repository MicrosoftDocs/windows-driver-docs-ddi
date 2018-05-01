---
UID: NF:video.VideoPortGetDeviceData
title: VideoPortGetDeviceData function
author: windows-driver-content
description: The VideoPortGetDeviceData function retrieves system-detected configuration information from the ..\Machine\Hardware\Description tree in the registry.
old-location: display\videoportgetdevicedata.htm
old-project: display
ms.assetid: 95df7ed6-ac9e-4620-bc3c-54e45a123fdc
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: VideoPortGetDeviceData, VideoPortGetDeviceData function [Display Devices], VideoPort_Functions_01e88665-7ecb-470e-b25b-21a3c62f7485.xml, display.videoportgetdevicedata, video/VideoPortGetDeviceData
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
-	VideoPortGetDeviceData
product: Windows
targetos: Windows
req.typenames: 
---

# VideoPortGetDeviceData function


## -description


The <b>VideoPortGetDeviceData</b> function retrieves system-detected configuration information from the <b>..\Machine\Hardware\Description</b> tree in the registry. This information is bus-specific or adapter-specific and stored in the registry by the system loader or the HAL.


## -parameters




### -param HwDeviceExtension

Pointer to the miniport driver's device extension.


### -param DeviceDataType

Specifies the type of data being requested as a VIDEO_DEVICE_DATA_TYPE value, typically one of <b>VpBusData</b>, <b>VpControllerData</b>, or <b>VpMonitorData.</b>

The <b>VpControllerData</b> and <b>VpMonitorData</b> values are relevant only on ARC-compliant platforms. Miniport drivers of x86-type video adapters generally specify <b>VpBusData</b>, particularly for adapters on EISA buses. The <b>VpMachineData</b> value is reserved for future use.


### -param CallbackRoutine

Pointer to a driver-supplied <a href="https://msdn.microsoft.com/81c3f484-427e-43b8-b7dd-12017533560b">HwVidQueryDeviceCallback</a> function to be called with the requested information.


### -param Context

Pointer to a caller-determined context parameter to be passed to the <i>CallbackRoutine</i>. It typically points to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570531">VIDEO_PORT_CONFIG_INFO</a> buffer.


## -returns



<b>VideoPortGetDeviceData</b> returns NO_ERROR if it successfully called the miniport driver's <i>HwVidQueryDeviceCallback</i> function with configuration information.




## -remarks



<b>VideoPortGetDeviceData</b> cannot be called from a miniport driver's <a href="https://msdn.microsoft.com/523471e3-cf1e-48d2-b5f0-2f8d19ad71e0">HwVidInterrupt</a> or <a href="https://msdn.microsoft.com/bd41bbbf-4ec8-4e6c-8620-d8a9fe0b8bad">HwVidTimer</a> functions, or from <a href="https://msdn.microsoft.com/library/windows/hardware/ff570339">VideoPortQueueDpc</a>, or from a callback to <a href="https://msdn.microsoft.com/library/windows/hardware/ff570372">VideoPortSynchronizeExecution</a>.

The registry tree from which <b>VideoPortGetDeviceData</b> retrieves configuration information is <i>volatile</i>; that is, it is re-created by the system loader or HAL every time the system is loaded. Because this information is collected and stored early in the boot process, the bus-relative configuration information returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff570306">VideoPortGetBusData</a> can be more complete. 




## -see-also




<a href="https://msdn.microsoft.com/8c880eff-4b4c-439e-9239-f2343c1fe084">HwVidFindAdapter</a>



<a href="https://msdn.microsoft.com/81c3f484-427e-43b8-b7dd-12017533560b">HwVidQueryDeviceCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570531">VIDEO_PORT_CONFIG_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570316">VideoPortGetRegistryParameters</a>
 

 

