---
UID: NF:video.VideoPortGetRegistryParameters
title: VideoPortGetRegistryParameters function
author: windows-driver-content
description: The VideoPortGetRegistryParameters function retrieves device-specific configuration information under the adapter key in the registry at startup.
old-location: display\videoportgetregistryparameters.htm
old-project: display
ms.assetid: beca2e83-df56-4ed0-8ea8-b0090e574cd3
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: VideoPortGetRegistryParameters, VideoPortGetRegistryParameters function [Display Devices], VideoPort_Functions_f4e1230a-ae49-4751-8c60-e05043dbb049.xml, display.videoportgetregistryparameters, video/VideoPortGetRegistryParameters
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
-	VideoPortGetRegistryParameters
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
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

TBD


### -param Context

Pointer to a caller-determined context parameter to be passed to the <i>CallbackRoutine</i>, typically the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570531">VIDEO_PORT_CONFIG_INFO</a> buffer.


#### - CallbackRoutine

Pointer to the miniport driver's <a href="https://msdn.microsoft.com/90020700-b9c8-42e6-bafa-908cbc3eb233">HwVidQueryNamedValueCallback</a> function.


## -returns



<b>VideoPortGetRegistryParameters</b> returns NO_ERROR if it successfully collected the requested information and called the miniport driver's <i>HwVidQueryNamedValueCallback</i> function; otherwise returns ERROR_INVALID_PARAMETER.




## -remarks



<b>VideoPortGetRegistryParameters</b> cannot be called from a miniport driver's <a href="https://msdn.microsoft.com/523471e3-cf1e-48d2-b5f0-2f8d19ad71e0">HwVidInterrupt</a> or <a href="https://msdn.microsoft.com/bd41bbbf-4ec8-4e6c-8620-d8a9fe0b8bad">HwVidTimer</a> functions, or from <a href="https://msdn.microsoft.com/library/windows/hardware/ff570339">VideoPortQueueDpc</a>, or from a callback to <a href="https://msdn.microsoft.com/library/windows/hardware/ff570372">VideoPortSynchronizeExecution</a>.

For Windows XP and later operating system versions, the <i>ParameterName</i> parameter can contain a path that exactly references a value name one or more levels below the <b>adapter</b> key. For example, the string "SubKey1\Value1" can be used to obtain the value entry for the Value1 value number under the SubKey1 subkey. 

The registry key from which <b>VideoPortGetRegistryParameters</b> retrieves configuration information cannot contain any information about the corresponding display driver, because miniport driver <a href="https://msdn.microsoft.com/8c880eff-4b4c-439e-9239-f2343c1fe084">HwVidFindAdapter</a> functions execute before any display driver is loaded.

Miniport drivers should not query configuration information stored in the <b>DefaultSettings</b> entries, which may not be supported in later versions of the operating system. 




## -see-also




<a href="https://msdn.microsoft.com/8c880eff-4b4c-439e-9239-f2343c1fe084">HwVidFindAdapter</a>



<a href="https://msdn.microsoft.com/0e43de21-59e5-4368-8ea2-34fa52e99950">HwVidInitialize</a>



<a href="https://msdn.microsoft.com/81c3f484-427e-43b8-b7dd-12017533560b">HwVidQueryDeviceCallback</a>



<a href="https://msdn.microsoft.com/90020700-b9c8-42e6-bafa-908cbc3eb233">HwVidQueryNamedValueCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570531">VIDEO_PORT_CONFIG_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570298">VideoPortFlushRegistry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570311">VideoPortGetDeviceData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570365">VideoPortSetRegistryParameters</a>
 

 

