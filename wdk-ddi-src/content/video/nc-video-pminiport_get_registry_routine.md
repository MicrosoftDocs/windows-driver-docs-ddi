---
UID: NC:video.PMINIPORT_GET_REGISTRY_ROUTINE
title: PMINIPORT_GET_REGISTRY_ROUTINE
author: windows-driver-content
description: HwVidQueryNamedValueCallback processes the specified data retrieved from the registry.
old-location: display\hwvidquerynamedvaluecallback.htm
tech.root: display
ms.assetid: 90020700-b9c8-42e6-bafa-908cbc3eb233
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: HwVidQueryNamedValueCallback, HwVidQueryNamedValueCallback callback function [Display Devices], PMINIPORT_GET_REGISTRY_ROUTINE, PMINIPORT_GET_REGISTRY_ROUTINE callback, VideoMiniport_Functions_4e6a63e7-cf5f-4cb6-9e9a-10286e40d762.xml, display.hwvidquerynamedvaluecallback, video/HwVidQueryNamedValueCallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	video.h
api_name:
-	HwVidQueryNamedValueCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# PMINIPORT_GET_REGISTRY_ROUTINE callback function


## -description


<i>HwVidQueryNamedValueCallback</i> processes the specified data retrieved from the registry.


## -parameters




### -param HwDeviceExtension

Pointer to the miniport driver's per-adapter storage area. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543119">Device Extensions</a>.


### -param Context

Pointer to a driver-determined context specified as input to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570316">VideoPortGetRegistryParameters</a> function.


### -param ValueName

Pointer to a NULL-terminated Unicode string naming the entry.


### -param ValueData

Pointer to the buffered data associated with <i>ValueName</i>, supplied by <b>VideoPortGetRegistryParameters</b>.


### -param ValueLength

Specifies the size in bytes of the buffer at <i>ValueData</i>.


## -returns



<i>HwVidQueryNamedValueCallback</i> returns the status of the operation.




## -remarks



<i>HwVidQueryNamedValueCallback</i> is an optional miniport driver function passed in a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff570316">VideoPortGetRegistryParameters</a>.

<b>VideoPortGetRegistryParameters</b> calls <i>HwVidQueryNamedValueCallback</i> after collecting available configuration information about the given <i>ValueName</i> in the <b>adapter</b> key of the registry. 

<i>HwVidFindAdapter</i> or <a href="https://msdn.microsoft.com/0e43de21-59e5-4368-8ea2-34fa52e99950">HwVidInitialize</a> can call <b>VideoPortGetRegistryParameters</b> with a driver-supplied <i>HwVidQueryNamedValueCallback</i> function, pointers to the device extension and any driver-supplied context data (which can be the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570531">VIDEO_PORT_CONFIG_INFO</a> buffer), and a pointer to a Unicode string naming the value to be retrieved from the registry.

<i>HwVidFindAdapter</i> or <i>HwVidInitialize</i> can set <b>VideoPortGetRegistryParameters</b>'s <i>IsFileNameParameter</i> argument to <b>TRUE</b> if the driver-supplied Unicode string is a named registry entry whose value is a file name. For this specification, the returned data will be the contents of the named file.

When <b>VideoPortGetRegistryParameters</b> calls the <i>HwVidQueryNamedValueCallback</i> function, it processes whatever configuration data is made available. For example, <i>HwVidQueryNamedValueCallback</i> might use retrieved data to determine the miniport driver's access ranges and to set up its emulator access ranges (if any), interrupt vector or interrupt IRQL (if any), and so forth in the VIDEO_PORT_CONFIG_INFO buffer, as well as in the miniport driver's device extension, before returning control to the <i>HwVidFindAdapter</i> function.

<i>HwVidInitialize</i> might also call <b>VideoPortGetRegistryParameters</b> with <i>IsFileNameParameter</i> set to <b>TRUE</b> so that the miniport driver-supplied <i>HwVidQueryNamedValueCallback</i> function could use the buffered contents of a named file to set up microcode on the adapter.

The returned <i>ValueData</i> is on the stack, so it can be referenced locally. <i>HwVidQueryNamedValueCallback</i> can store some or all of the returned information for use by other miniport driver functions in the input <i>HwDeviceExtension</i> or use the input <i>Context</i> as a pointer to a location where the data can be stored.

<i>HwVidQueryNamedValueCallback</i> should be made pageable.




## -see-also




<a href="https://msdn.microsoft.com/8c880eff-4b4c-439e-9239-f2343c1fe084">HwVidFindAdapter</a>



<a href="https://msdn.microsoft.com/0e43de21-59e5-4368-8ea2-34fa52e99950">HwVidInitialize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570531">VIDEO_PORT_CONFIG_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570316">VideoPortGetRegistryParameters</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570365">VideoPortSetRegistryParameters</a>
 

 

