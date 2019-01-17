---
UID: NF:video.VideoPortVerifyAccessRanges
title: VideoPortVerifyAccessRanges function
description: The VideoPortVerifyAccessRanges function checks the registry for whether another driver has already claimed ownership of the specified bus-relative access ranges and any other hardware resources specified in the VIDEO_PORT_CONFIG_INFO structure.
old-location: display\videoportverifyaccessranges.htm
tech.root: display
ms.assetid: 067ecebb-e63c-4161-9e8f-3746ecad3259
ms.date: 05/10/2018
ms.keywords: VideoPortVerifyAccessRanges, VideoPortVerifyAccessRanges function [Display Devices], VideoPort_Functions_be1c2439-0fde-4d2e-a892-9a64e19f9970.xml, display.videoportverifyaccessranges, video/VideoPortVerifyAccessRanges
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
-	VideoPortVerifyAccessRanges
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortVerifyAccessRanges function


## -description


The <b>VideoPortVerifyAccessRanges</b> function checks the registry for whether another driver has already claimed ownership of the specified bus-relative access ranges and any other hardware resources specified in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570531">VIDEO_PORT_CONFIG_INFO</a> structure. If not, this function claims the given resources for the caller.


## -parameters

### -param HwDeviceExtension

Pointer to the miniport driver's device extension.

### -param NumAccessRanges

Specifies the number of elements in the <i>AccessRanges</i> array, or zero.

### -param AccessRanges [in, optional]

Pointer to the miniport driver's access ranges array, or <b>NULL</b>. Each <a href="https://msdn.microsoft.com/library/windows/hardware/ff570498">VIDEO_ACCESS_RANGE</a>-type element in this array specifies a bus-relative range of device memory, I/O ports, or register addresses for the adapter.

## -returns

<b>VideoPortVerifyAccessRanges</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|ERROR_INVALID_PARAMETER|An error occurred or a conflict was found; that is, another driver has already claimed one or more of the given hardware resources for its device.|
|NO_ERROR|The given AccessRanges are valid and have been claimed for use by the caller.|

## -remarks



Every video miniport driver either must call <b>VideoPortVerifyAccessRanges</b>, or use access ranges returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff570302">VideoPortGetAccessRanges</a> before attempting to access a video adapter during the driver (and system) initialization process.

<b>VideoPortVerifyAccessRanges</b> can be called only by a miniport driver's <a href="https://msdn.microsoft.com/8c880eff-4b4c-439e-9239-f2343c1fe084">HwVidFindAdapter</a> function.

Every video miniport driver must define the bus-relative access ranges for its device, either as statically allocated memory in the driver's header file or code or on the stack. Most miniport drivers set up their video access ranges on the stack, except for those that use PC standard address ranges for video memory, such as VGA-compatible SVGA miniport drivers.

The <i>HwVidFindAdapter</i> function should try to obtain bus-relative access range information by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff570302">VideoPortGetAccessRanges</a>, or by checking the registry through calls to <a href="https://msdn.microsoft.com/library/windows/hardware/ff570311">VideoPortGetDeviceData</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff570316">VideoPortGetRegistryParameters</a>. If <a href="https://msdn.microsoft.com/8c880eff-4b4c-439e-9239-f2343c1fe084">HwVidFindAdapter</a> cannot get this information, the miniport driver should have a set of bus-relative default values for access ranges.

If a miniport driver's access ranges are externally configurable, the installation program sets up access ranges for the adapter in the registry. Such a miniport driver's <i>HwVidFindAdapter</i> function can call <b>VideoPortGetRegistryParameters</b> with a miniport driver-supplied <a href="https://msdn.microsoft.com/90020700-b9c8-42e6-bafa-908cbc3eb233">HwVidQueryNamedValueCallback</a> function that processes information retrieved from the registry.


<a href="https://msdn.microsoft.com/8c880eff-4b4c-439e-9239-f2343c1fe084">HwVidFindAdapter</a> must not pass any access range addresses to <a href="https://msdn.microsoft.com/library/windows/hardware/ff570310">VideoPortGetDeviceBase</a> unless it calls <b>VideoPortVerifyAccessRanges</b> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff570302">VideoPortGetAccessRanges</a> first and the respective function returns NO_ERROR.

<b>VideoPortVerifyAccessRanges</b> can be called again if the initial <i>AccessRanges</i> specification or value in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570531">VIDEO_PORT_CONFIG_INFO</a>, such as an interrupt vector, causes it to return an ERROR_<i>XXX</i> indicating that another driver has already claimed the resource(s).

If <b>VideoPortVerifyAccessRanges</b> returns NO_ERROR, a subsequent call for the same adapter overwrites the miniport driver's claim on resources for that adapter in the registry.

Note that a miniport driver cannot communicate with its video adapter, except by using mapped addresses returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff570310">VideoPortGetDeviceBase</a> with the <b>VideoPortRead/Write</b><i>Xxx</i> functions.

If the <a href="https://msdn.microsoft.com/8c880eff-4b4c-439e-9239-f2343c1fe084">HwVidFindAdapter</a> function claims bus-relative access ranges and possibly other hardware resources for an adapter but then determines that it does not support the adapter, the miniport driver must relinquish its claims on hardware resources in the registry by calling <b>VideoPortVerifyAccessRanges</b> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff570302">VideoPortGetAccessRanges</a> with <i>NumAccessRanges</i> set to zero and <i>AccessRanges</i> set to <b>NULL</b>.

To relinquish claims on a subset of claimed access ranges that the miniport driver is no longer using, do the following:

<ol>
<li>
Modify the <i>AccessRanges</i> specification for the adapter so that each element describing a range to be released still has <b>RangeStart</b> set to the bus-relative base of a claimed range, but <b>RangeLength</b> reset to zero.

</li>
<li>
Call <b>VideoPortVerifyAccessRanges</b> with this modified <i>AccessRanges</i> array.

</li>
</ol>



## -see-also




<a href="https://msdn.microsoft.com/8c880eff-4b4c-439e-9239-f2343c1fe084">HwVidFindAdapter</a>



<a href="https://msdn.microsoft.com/81c3f484-427e-43b8-b7dd-12017533560b">HwVidQueryDeviceCallback</a>



<a href="https://msdn.microsoft.com/90020700-b9c8-42e6-bafa-908cbc3eb233">HwVidQueryNamedValueCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570498">VIDEO_ACCESS_RANGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570531">VIDEO_PORT_CONFIG_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570302">VideoPortGetAccessRanges</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570310">VideoPortGetDeviceBase</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570311">VideoPortGetDeviceData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570316">VideoPortGetRegistryParameters</a>
 

 

