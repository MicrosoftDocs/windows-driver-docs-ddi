---
UID: NF:video.VideoPortVerifyAccessRanges
title: VideoPortVerifyAccessRanges function
author: windows-driver-content
description: The VideoPortVerifyAccessRanges function checks the registry for whether another driver has already claimed ownership of the specified bus-relative access ranges and any other hardware resources specified in the VIDEO_PORT_CONFIG_INFO structure.
old-location: display\videoportverifyaccessranges.htm
old-project: display
ms.assetid: 067ecebb-e63c-4161-9e8f-3746ecad3259
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: VideoPortVerifyAccessRanges, VideoPortVerifyAccessRanges function [Display Devices], VideoPort_Functions_be1c2439-0fde-4d2e-a892-9a64e19f9970.xml, display.videoportverifyaccessranges, video/VideoPortVerifyAccessRanges
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
-	VideoPortVerifyAccessRanges
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortVerifyAccessRanges function


## -description


The <b>VideoPortVerifyAccessRanges</b> function checks the registry for whether another driver has already claimed ownership of the specified bus-relative access ranges and any other hardware resources specified in the <a href="..\video\ns-video-_video_port_config_info.md">VIDEO_PORT_CONFIG_INFO</a> structure. If not, this function claims the given resources for the caller.


## -syntax


````
VP_STATUS VideoPortVerifyAccessRanges(
           PVOID               HwDeviceExtension,
           ULONG               NumAccessRanges,
  _In_opt_ PVIDEO_ACCESS_RANGE AccessRanges
);
````


## -parameters




### -param HwDeviceExtension

Pointer to the miniport driver's device extension.


### -param NumAccessRanges

Specifies the number of elements in the <i>AccessRanges</i> array, or zero.


### -param AccessRanges [in, optional]

Pointer to the miniport driver's access ranges array, or <b>NULL</b>. Each <a href="..\video\ns-video-_video_access_range.md">VIDEO_ACCESS_RANGE</a>-type element in this array specifies a bus-relative range of device memory, I/O ports, or register addresses for the adapter.


## -returns



<b>VideoPortVerifyAccessRanges</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>ERROR_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An error occurred or a conflict was found; that is, another driver has already claimed one or more of the given hardware resources for its device.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NO_ERROR</b></dt>
</dl>
</td>
<td width="60%">
The given <i>AccessRanges</i> are valid and have been claimed for use by the caller.

</td>
</tr>
</table>
 




## -remarks



Every video miniport driver either must call <b>VideoPortVerifyAccessRanges</b>, or use access ranges returned by <a href="..\video\nf-video-videoportgetaccessranges.md">VideoPortGetAccessRanges</a> before attempting to access a video adapter during the driver (and system) initialization process.

<b>VideoPortVerifyAccessRanges</b> can be called only by a miniport driver's <a href="..\video\nc-video-pvideo_hw_find_adapter.md">HwVidFindAdapter</a> function.

Every video miniport driver must define the bus-relative access ranges for its device, either as statically allocated memory in the driver's header file or code or on the stack. Most miniport drivers set up their video access ranges on the stack, except for those that use PC standard address ranges for video memory, such as VGA-compatible SVGA miniport drivers.

The <i>HwVidFindAdapter</i> function should try to obtain bus-relative access range information by calling <a href="..\video\nf-video-videoportgetaccessranges.md">VideoPortGetAccessRanges</a>, or by checking the registry through calls to <a href="..\video\nf-video-videoportgetdevicedata.md">VideoPortGetDeviceData</a> or <a href="..\video\nf-video-videoportgetregistryparameters.md">VideoPortGetRegistryParameters</a>. If <a href="..\video\nc-video-pvideo_hw_find_adapter.md">HwVidFindAdapter</a> cannot get this information, the miniport driver should have a set of bus-relative default values for access ranges.

If a miniport driver's access ranges are externally configurable, the installation program sets up access ranges for the adapter in the registry. Such a miniport driver's <i>HwVidFindAdapter</i> function can call <b>VideoPortGetRegistryParameters</b> with a miniport driver-supplied <a href="..\video\nc-video-pminiport_get_registry_routine.md">HwVidQueryNamedValueCallback</a> function that processes information retrieved from the registry.


<a href="..\video\nc-video-pvideo_hw_find_adapter.md">HwVidFindAdapter</a> must not pass any access range addresses to <a href="..\video\nf-video-videoportgetdevicebase.md">VideoPortGetDeviceBase</a> unless it calls <b>VideoPortVerifyAccessRanges</b> or <a href="..\video\nf-video-videoportgetaccessranges.md">VideoPortGetAccessRanges</a> first and the respective function returns NO_ERROR.

<b>VideoPortVerifyAccessRanges</b> can be called again if the initial <i>AccessRanges</i> specification or value in the <a href="..\video\ns-video-_video_port_config_info.md">VIDEO_PORT_CONFIG_INFO</a>, such as an interrupt vector, causes it to return an ERROR_<i>XXX</i> indicating that another driver has already claimed the resource(s).

If <b>VideoPortVerifyAccessRanges</b> returns NO_ERROR, a subsequent call for the same adapter overwrites the miniport driver's claim on resources for that adapter in the registry.

Note that a miniport driver cannot communicate with its video adapter, except by using mapped addresses returned by <a href="..\video\nf-video-videoportgetdevicebase.md">VideoPortGetDeviceBase</a> with the <b>VideoPortRead/Write</b><i>Xxx</i> functions.

If the <a href="..\video\nc-video-pvideo_hw_find_adapter.md">HwVidFindAdapter</a> function claims bus-relative access ranges and possibly other hardware resources for an adapter but then determines that it does not support the adapter, the miniport driver must relinquish its claims on hardware resources in the registry by calling <b>VideoPortVerifyAccessRanges</b> or <a href="..\video\nf-video-videoportgetaccessranges.md">VideoPortGetAccessRanges</a> with <i>NumAccessRanges</i> set to zero and <i>AccessRanges</i> set to <b>NULL</b>.

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

<a href="..\video\ns-video-_video_port_config_info.md">VIDEO_PORT_CONFIG_INFO</a>



<a href="..\video\nf-video-videoportgetaccessranges.md">VideoPortGetAccessRanges</a>



<a href="..\video\nc-video-pminiport_query_device_routine.md">HwVidQueryDeviceCallback</a>



<a href="..\video\nf-video-videoportgetdevicebase.md">VideoPortGetDeviceBase</a>



<a href="..\video\nf-video-videoportgetregistryparameters.md">VideoPortGetRegistryParameters</a>



<a href="..\video\nc-video-pminiport_get_registry_routine.md">HwVidQueryNamedValueCallback</a>



<a href="..\video\nf-video-videoportgetdevicedata.md">VideoPortGetDeviceData</a>



<a href="..\video\nc-video-pvideo_hw_find_adapter.md">HwVidFindAdapter</a>



<a href="..\video\ns-video-_video_access_range.md">VIDEO_ACCESS_RANGE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortVerifyAccessRanges function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

