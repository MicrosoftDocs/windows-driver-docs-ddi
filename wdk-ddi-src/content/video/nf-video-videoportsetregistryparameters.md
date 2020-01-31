---
UID: NF:video.VideoPortSetRegistryParameters
title: VideoPortSetRegistryParameters function (video.h)
description: The VideoPortSetRegistryParameters function writes information under the adapter key in the registry.
old-location: display\videoportsetregistryparameters.htm
tech.root: display
ms.assetid: 39cf1829-2caf-44e0-8528-acb0def0dd54
ms.date: 05/10/2018
ms.keywords: VideoPortSetRegistryParameters, VideoPortSetRegistryParameters function [Display Devices], VideoPort_Functions_a1d6dbfd-595b-4396-a1d3-9ec4fa3a6bfb.xml, display.videoportsetregistryparameters, video/VideoPortSetRegistryParameters
f1_keywords:
 - "video/VideoPortSetRegistryParameters"
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
- VideoPortSetRegistryParameters
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortSetRegistryParameters function


## -description


The <b>VideoPortSetRegistryParameters</b> function writes information under the <b>adapter</b> key in the registry.


## -parameters




### -param HwDeviceExtension

Pointer to the miniport driver's device extension.


### -param ValueName [in]

Pointer to a buffer containing a null-terminated Unicode string that names the value entry for which data is being written in the registry.


### -param ValueData [in]

Pointer to a buffer containing the values to be written for the <i>ValueName</i> entry.


### -param ValueLength

Specifies the size, in bytes, of the data to be written to the registry.


## -returns



<b>VideoPortSetRegistryParameters</b> returns NO_ERROR if the given data was successfully written to the registry. Otherwise, it can return ERROR_INVALID_PARAMETER.




## -remarks



<b>VideoPortSetRegistryParameters</b> searches under the registry's <b>adapter</b> key for the value name specified in the <i>ValueName</i> parameter. If the value name that is searched for does not exist, this function creates it automatically. When the value name is found or created, the contents of the <i>ValueData</i> parameter are copied to the value name. 

For Windows XP and later operating system versions, the value name specified in the <i>ValueName</i> parameters does not need to be directly associated with the <b>adapter</b> key. Instead, <i>ValueName</i> can be associated with a subkey whose path includes the <b>adapter</b> key. If the <i>ValueName</i> string contains one or more backslashes, <b>VideoPortSetRegistryParameters</b> searches for or creates the subkey whose value name is at the end of the string. 

For example, if <i>ValueName</i> is set to the string "SubKey1\Value1", this function searches for <b>SubKey1</b> under the <b>adapter</b> key in the registry, creating <b>SubKey1</b> if it does not exist. The function then searches for the <b>Value1</b> value name, creating it if necessary. <b>VideoPortSetRegistryParameters</b> then copies the contents of the <i>ValueData</i> parameter to the registry. The path specified in the <i>ValueName</i> parameter can refer to a value name an arbitrary number of levels below the <b>adapter</b> key, but the behavior of this function is essentially the same. If at any point a subkey or value name is not found, it is created automatically. 

In Windows 2000 and later, <b>VideoPortSetRegistryParameters</b> returns ERROR_INVALID_PARAMETER if the string passed in the <i>ValueName</i> parameter begins with "DefaultSettings." (note that the period is part of the string). In operating systems earlier than Windows 2000, a video miniport driver can pass a value name that begins with "DefaultSettings." to specify the default resolution for a monitor, but there is no need for that capability in Windows 2000 and later.

In a checked build of any version of the operating system, a value name that begins with "DefaultSettings." causes an assertion failure.

<b>VideoPortSetRegistryParameters</b> cannot be called from a miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_interrupt">HwVidInterrupt</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_timer">HwVidTimer</a> functions, or from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportqueuedpc">VideoPortQueueDpc</a>, or from a callback to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportsynchronizeexecution">VideoPortSynchronizeExecution</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_find_adapter">HwVidFindAdapter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_initialize">HwVidInitialize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportflushregistry">VideoPortFlushRegistry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetregistryparameters">VideoPortGetRegistryParameters</a>
 

 

