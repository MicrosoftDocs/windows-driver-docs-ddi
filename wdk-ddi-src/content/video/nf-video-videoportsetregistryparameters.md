---
UID: NF:video.VideoPortSetRegistryParameters
title: VideoPortSetRegistryParameters function
author: windows-driver-content
description: The VideoPortSetRegistryParameters function writes information under the adapter key in the registry.
old-location: display\videoportsetregistryparameters.htm
old-project: display
ms.assetid: 39cf1829-2caf-44e0-8528-acb0def0dd54
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: VideoPortSetRegistryParameters, VideoPortSetRegistryParameters function [Display Devices], VideoPort_Functions_a1d6dbfd-595b-4396-a1d3-9ec4fa3a6bfb.xml, display.videoportsetregistryparameters, video/VideoPortSetRegistryParameters
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
-	VideoPortSetRegistryParameters
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortSetRegistryParameters function


## -description


The <b>VideoPortSetRegistryParameters</b> function writes information under the <b>adapter</b> key in the registry.


## -syntax


````
VP_STATUS VideoPortSetRegistryParameters(
       PVOID HwDeviceExtension,
  _In_ PWSTR ValueName,
  _In_ PVOID ValueData,
       ULONG ValueLength
);
````


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

<b>VideoPortSetRegistryParameters</b> cannot be called from a miniport driver's <a href="..\video\nc-video-pvideo_hw_interrupt.md">HwVidInterrupt</a> or <a href="..\video\nc-video-pvideo_hw_timer.md">HwVidTimer</a> functions, or from <a href="..\video\nf-video-videoportqueuedpc.md">VideoPortQueueDpc</a>, or from a callback to <a href="..\video\nf-video-videoportsynchronizeexecution.md">VideoPortSynchronizeExecution</a>. 




## -see-also

<a href="..\video\nf-video-videoportgetregistryparameters.md">VideoPortGetRegistryParameters</a>



<a href="..\video\nf-video-videoportflushregistry.md">VideoPortFlushRegistry</a>



<a href="..\video\nc-video-pvideo_hw_initialize.md">HwVidInitialize</a>



<a href="..\video\nc-video-pvideo_hw_find_adapter.md">HwVidFindAdapter</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortSetRegistryParameters function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

