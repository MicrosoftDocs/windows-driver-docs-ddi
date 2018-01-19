---
UID: NF:video.VideoPortGetDeviceData
title: VideoPortGetDeviceData function
author: windows-driver-content
description: The VideoPortGetDeviceData function retrieves system-detected configuration information from the ..\Machine\Hardware\Description tree in the registry.
old-location: display\videoportgetdevicedata.htm
old-project: display
ms.assetid: 95df7ed6-ac9e-4620-bc3c-54e45a123fdc
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: VideoPortGetDeviceData
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
req.alt-api: VideoPortGetDeviceData
req.alt-loc: Videoprt.sys
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
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortGetDeviceData function



## -description
The <b>VideoPortGetDeviceData</b> function retrieves system-detected configuration information from the <b>..\Machine\Hardware\Description</b> tree in the registry. This information is bus-specific or adapter-specific and stored in the registry by the system loader or the HAL.



## -syntax

````
VP_STATUS VideoPortGetDeviceData(
   PVOID                          HwDeviceExtension,
   VIDEO_DEVICE_DATA_TYPE         DeviceDataType,
   PMINIPORT_QUERY_DEVICE_ROUTINE CallbackRoutine,
   PVOID                          Context
);
````


## -parameters

### -param HwDeviceExtension 

Pointer to the miniport driver's device extension.


### -param DeviceDataType 

Specifies the type of data being requested as a VIDEO_DEVICE_DATA_TYPE value, typically one of <b>VpBusData</b>, <b>VpControllerData</b>, or <b>VpMonitorData.</b>

The <b>VpControllerData</b> and <b>VpMonitorData</b> values are relevant only on ARC-compliant platforms. Miniport drivers of x86-type video adapters generally specify <b>VpBusData</b>, particularly for adapters on EISA buses. The <b>VpMachineData</b> value is reserved for future use.


### -param CallbackRoutine 

Pointer to a driver-supplied <a href="..\video\nc-video-pminiport_query_device_routine.md">HwVidQueryDeviceCallback</a> function to be called with the requested information.


### -param Context 

Pointer to a caller-determined context parameter to be passed to the <i>CallbackRoutine</i>. It typically points to the <a href="..\video\ns-video-_video_port_config_info.md">VIDEO_PORT_CONFIG_INFO</a> buffer.


## -returns
<b>VideoPortGetDeviceData</b> returns NO_ERROR if it successfully called the miniport driver's <i>HwVidQueryDeviceCallback</i> function with configuration information.


## -remarks
<b>VideoPortGetDeviceData</b> cannot be called from a miniport driver's <a href="..\video\nc-video-pvideo_hw_interrupt.md">HwVidInterrupt</a> or <a href="..\video\nc-video-pvideo_hw_timer.md">HwVidTimer</a> functions, or from <a href="..\video\nf-video-videoportqueuedpc.md">VideoPortQueueDpc</a>, or from a callback to <a href="..\video\nf-video-videoportsynchronizeexecution.md">VideoPortSynchronizeExecution</a>.

The registry tree from which <b>VideoPortGetDeviceData</b> retrieves configuration information is <i>volatile</i>; that is, it is re-created by the system loader or HAL every time the system is loaded. Because this information is collected and stored early in the boot process, the bus-relative configuration information returned by <a href="..\video\nf-video-videoportgetbusdata.md">VideoPortGetBusData</a> can be more complete. 


## -see-also
<dl>
<dt>
<a href="..\video\nc-video-pvideo_hw_find_adapter.md">HwVidFindAdapter</a>
</dt>
<dt>
<a href="..\video\nc-video-pminiport_query_device_routine.md">HwVidQueryDeviceCallback</a>
</dt>
<dt>
<a href="..\video\ns-video-_video_port_config_info.md">VIDEO_PORT_CONFIG_INFO</a>
</dt>
<dt>
<a href="..\video\nf-video-videoportgetregistryparameters.md">VideoPortGetRegistryParameters</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortGetDeviceData function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

