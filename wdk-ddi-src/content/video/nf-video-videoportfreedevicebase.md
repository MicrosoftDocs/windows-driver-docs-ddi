---
UID: NF:video.VideoPortFreeDeviceBase
title: VideoPortFreeDeviceBase function (video.h)
description: The VideoPortFreeDeviceBase function frees a range of bus-relative device I/O ports or memory addresses previously mapped into the system address space. It does this by calling VideoPortGetDeviceBase.
old-location: display\videoportfreedevicebase.htm
tech.root: display
ms.assetid: 5b165237-f6fb-449c-878d-0ee09076d203
ms.date: 05/10/2018
ms.keywords: VideoPortFreeDeviceBase, VideoPortFreeDeviceBase function [Display Devices], VideoPort_Functions_cdbada9a-c5be-48e3-90e7-9414a055350c.xml, display.videoportfreedevicebase, video/VideoPortFreeDeviceBase
f1_keywords:
 - "video/VideoPortFreeDeviceBase"
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
- VideoPortFreeDeviceBase
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortFreeDeviceBase function


## -description


The <b>VideoPortFreeDeviceBase</b> function frees a range of bus-relative device I/O ports or memory addresses previously mapped into the system address space. It does this by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>.


## -parameters




### -param HwDeviceExtension

Pointer to the miniport driver's device extension.


### -param MappedAddress

Specifies the base address of the mapped range to be freed. This value must be the same as the value returned by a preceding call to <b>VideoPortGetDeviceBase</b>.


## -returns



None




## -remarks



<b>VideoPortFreeDeviceBase</b> must be called from the miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_find_adapter">HwVidFindAdapter</a> function if the miniport driver has already mapped an address range for an adapter it cannot support or does not use any longer.

When this occurs, the miniport driver also must release its claim on the corresponding hardware resources in the registry. To release all claims on resources for a particular adapter, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportverifyaccessranges">VideoPortVerifyAccessRanges</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetaccessranges">VideoPortGetAccessRanges</a> with the <i>NumAccessRanges</i> parameter set to zero. To release claims on selected access ranges, do the following:

<ol>
<li>
Modify the access ranges array of claimed bus-relative ranges for the adapter by setting the appropriate elements' <b>RangeLength</b>(s) to zero. Leave the current specification as is in all elements on which the miniport driver will not release its claims.

</li>
<li>
Call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportverifyaccessranges">VideoPortVerifyAccessRanges</a> with this modified <i>AccessRanges</i> array.

</li>
</ol>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_find_adapter">HwVidFindAdapter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetaccessranges">VideoPortGetAccessRanges</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportverifyaccessranges">VideoPortVerifyAccessRanges</a>
 

 

