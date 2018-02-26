---
UID: NF:video.VideoPortGetRegistryParameters
title: VideoPortGetRegistryParameters function
author: windows-driver-content
description: The VideoPortGetRegistryParameters function retrieves device-specific configuration information under the adapter key in the registry at startup.
old-location: display\videoportgetregistryparameters.htm
old-project: display
ms.assetid: beca2e83-df56-4ed0-8ea8-b0090e574cd3
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , G, P, R, V, VideoPortGetRegistryParameters, VideoPortGetRegistryParameters function [Display Devices], VideoPort_Functions_f4e1230a-ae49-4751-8c60-e05043dbb049.xml, a, d, display.videoportgetregistryparameters, e, g, i, m, o, r, s, t, video/VideoPortGetRegistryParameters, y"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Videoprt.sys
apiname:
-	VideoPortGetRegistryParameters
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortGetRegistryParameters function


## -description


The <b>VideoPortGetRegistryParameters</b> function retrieves device-specific configuration information under the<b> adapter </b>key in the registry at startup.


## -syntax


````
VP_STATUS VideoPortGetRegistryParameters(
       PVOID                          HwDeviceExtension,
  _In_ PWSTR                          ParameterName,
       UCHAR                          IsParameterFileName,
       PMINIPORT_GET_REGISTRY_ROUTINE CallbackRoutine,
       PVOID                          Context
);
````


## -parameters




### -param HwDeviceExtension

Pointer to the miniport driver's device extension.


### -param ParameterName [in]

Pointer to a NULL-terminated Unicode string that names the value entry to be retrieved from the registry. See the <b>Remarks</b> section for more information.


### -param IsParameterFileName

If the value is <b>TRUE</b>, the data value normally returned is treated as a file name. In that case, the buffered contents of that file are returned, rather than the parameter itself.


### -param GetRegistryRoutine

TBD


### -param Context

Pointer to a caller-determined context parameter to be passed to the <i>CallbackRoutine</i>, typically the <a href="..\video\ns-video-_video_port_config_info.md">VIDEO_PORT_CONFIG_INFO</a> buffer.


#### - CallbackRoutine

Pointer to the miniport driver's <a href="..\video\nc-video-pminiport_get_registry_routine.md">HwVidQueryNamedValueCallback</a> function.


## -returns



<b>VideoPortGetRegistryParameters</b> returns NO_ERROR if it successfully collected the requested information and called the miniport driver's <i>HwVidQueryNamedValueCallback</i> function; otherwise returns ERROR_INVALID_PARAMETER.




## -remarks



<b>VideoPortGetRegistryParameters</b> cannot be called from a miniport driver's <a href="..\video\nc-video-pvideo_hw_interrupt.md">HwVidInterrupt</a> or <a href="..\video\nc-video-pvideo_hw_timer.md">HwVidTimer</a> functions, or from <a href="..\video\nf-video-videoportqueuedpc.md">VideoPortQueueDpc</a>, or from a callback to <a href="..\video\nf-video-videoportsynchronizeexecution.md">VideoPortSynchronizeExecution</a>.

For Windows XP and later operating system versions, the <i>ParameterName</i> parameter can contain a path that exactly references a value name one or more levels below the <b>adapter</b> key. For example, the string "SubKey1\Value1" can be used to obtain the value entry for the Value1 value number under the SubKey1 subkey. 

The registry key from which <b>VideoPortGetRegistryParameters</b> retrieves configuration information cannot contain any information about the corresponding display driver, because miniport driver <a href="..\video\nc-video-pvideo_hw_find_adapter.md">HwVidFindAdapter</a> functions execute before any display driver is loaded.

Miniport drivers should not query configuration information stored in the <b>DefaultSettings</b> entries, which may not be supported in later versions of the operating system. 




## -see-also

<a href="..\video\ns-video-_video_port_config_info.md">VIDEO_PORT_CONFIG_INFO</a>



<a href="..\video\nc-video-pvideo_hw_initialize.md">HwVidInitialize</a>



<a href="..\video\nf-video-videoportgetdevicedata.md">VideoPortGetDeviceData</a>



<a href="..\video\nc-video-pvideo_hw_find_adapter.md">HwVidFindAdapter</a>



<a href="..\video\nf-video-videoportflushregistry.md">VideoPortFlushRegistry</a>



<a href="..\video\nc-video-pminiport_query_device_routine.md">HwVidQueryDeviceCallback</a>



<a href="..\video\nc-video-pminiport_get_registry_routine.md">HwVidQueryNamedValueCallback</a>



<a href="..\video\nf-video-videoportsetregistryparameters.md">VideoPortSetRegistryParameters</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortGetRegistryParameters function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

