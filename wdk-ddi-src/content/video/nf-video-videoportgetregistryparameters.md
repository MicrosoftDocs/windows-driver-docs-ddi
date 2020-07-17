---
UID: NF:video.VideoPortGetRegistryParameters
title: VideoPortGetRegistryParameters function (video.h)
description: The VideoPortGetRegistryParameters function retrieves device-specific configuration information under the adapter key in the registry at startup.
old-location: display\videoportgetregistryparameters.htm
tech.root: display
ms.assetid: beca2e83-df56-4ed0-8ea8-b0090e574cd3
ms.date: 05/10/2018
keywords: ["VideoPortGetRegistryParameters function"]
ms.keywords: VideoPortGetRegistryParameters, VideoPortGetRegistryParameters function [Display Devices], VideoPort_Functions_f4e1230a-ae49-4751-8c60-e05043dbb049.xml, display.videoportgetregistryparameters, video/VideoPortGetRegistryParameters
f1_keywords:
 - "video/VideoPortGetRegistryParameters"
 - "VideoPortGetRegistryParameters"
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
- VideoPortGetRegistryParameters
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortGetRegistryParameters function


## -description


The <b>VideoPortGetRegistryParameters</b> function retrieves device-specific configuration information under the<b> adapter </b>key in the registry at startup.


## -parameters




### -param HwDeviceExtension

Pointer to the miniport driver's device extension.


### -param ParameterName [in]

Pointer to a NULL-terminated Unicode string that names the value entry to be retrieved from the registry. See the <b>Remarks</b> section for more information.


### -param IsParameterFileName

If the value is <b>TRUE</b>, the data value normally returned is treated as a file name. In that case, the buffered contents of that file are returned, rather than the parameter itself.


### -param GetRegistryRoutine

Pointer to the miniport driver's [HwVidQueryNamedValueCallback](nc-video-pminiport_get_registry_routine.md) function.


### -param Context

Pointer to a caller-determined context parameter to be passed to the <i>CallbackRoutine</i>, typically the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_port_config_info">VIDEO_PORT_CONFIG_INFO</a> buffer.




## -returns



<b>VideoPortGetRegistryParameters</b> returns NO_ERROR if it successfully collected the requested information and called the miniport driver's <i>HwVidQueryNamedValueCallback</i> function; otherwise returns ERROR_INVALID_PARAMETER.




## -remarks



<b>VideoPortGetRegistryParameters</b> cannot be called from a miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_interrupt">HwVidInterrupt</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_timer">HwVidTimer</a> functions, or from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportqueuedpc">VideoPortQueueDpc</a>, or from a callback to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportsynchronizeexecution">VideoPortSynchronizeExecution</a>.

For Windows XP and later operating system versions, the <i>ParameterName</i> parameter can contain a path that exactly references a value name one or more levels below the <b>adapter</b> key. For example, the string "SubKey1\Value1" can be used to obtain the value entry for the Value1 value number under the SubKey1 subkey. 

The registry key from which <b>VideoPortGetRegistryParameters</b> retrieves configuration information cannot contain any information about the corresponding display driver, because miniport driver <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_find_adapter">HwVidFindAdapter</a> functions execute before any display driver is loaded.

Miniport drivers should not query configuration information stored in the <b>DefaultSettings</b> entries, which may not be supported in later versions of the operating system. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_find_adapter">HwVidFindAdapter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_initialize">HwVidInitialize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pminiport_query_device_routine">HwVidQueryDeviceCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pminiport_get_registry_routine">HwVidQueryNamedValueCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_port_config_info">VIDEO_PORT_CONFIG_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportflushregistry">VideoPortFlushRegistry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicedata">VideoPortGetDeviceData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportsetregistryparameters">VideoPortSetRegistryParameters</a>
 

 

