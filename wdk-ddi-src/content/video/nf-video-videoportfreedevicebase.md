---
UID: NF:video.VideoPortFreeDeviceBase
title: VideoPortFreeDeviceBase function
author: windows-driver-content
description: The VideoPortFreeDeviceBase function frees a range of bus-relative device I/O ports or memory addresses previously mapped into the system address space. It does this by calling VideoPortGetDeviceBase.
old-location: display\videoportfreedevicebase.htm
old-project: display
ms.assetid: 5b165237-f6fb-449c-878d-0ee09076d203
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: VideoPortFreeDeviceBase, VideoPortFreeDeviceBase function [Display Devices], VideoPort_Functions_cdbada9a-c5be-48e3-90e7-9414a055350c.xml, display.videoportfreedevicebase, video/VideoPortFreeDeviceBase
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
-	VideoPortFreeDeviceBase
product:
- Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortFreeDeviceBase function


## -description


The <b>VideoPortFreeDeviceBase</b> function frees a range of bus-relative device I/O ports or memory addresses previously mapped into the system address space. It does this by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff570310">VideoPortGetDeviceBase</a>.


## -parameters




### -param HwDeviceExtension

Pointer to the miniport driver's device extension.


### -param MappedAddress

Specifies the base address of the mapped range to be freed. This value must be the same as the value returned by a preceding call to <b>VideoPortGetDeviceBase</b>.


## -returns



None




## -remarks



<b>VideoPortFreeDeviceBase</b> must be called from the miniport driver's <a href="https://msdn.microsoft.com/8c880eff-4b4c-439e-9239-f2343c1fe084">HwVidFindAdapter</a> function if the miniport driver has already mapped an address range for an adapter it cannot support or does not use any longer.

When this occurs, the miniport driver also must release its claim on the corresponding hardware resources in the registry. To release all claims on resources for a particular adapter, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff570377">VideoPortVerifyAccessRanges</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff570302">VideoPortGetAccessRanges</a> with the <i>NumAccessRanges</i> parameter set to zero. To release claims on selected access ranges, do the following:

<ol>
<li>
Modify the access ranges array of claimed bus-relative ranges for the adapter by setting the appropriate elements' <b>RangeLength</b>(s) to zero. Leave the current specification as is in all elements on which the miniport driver will not release its claims.

</li>
<li>
Call <a href="https://msdn.microsoft.com/library/windows/hardware/ff570377">VideoPortVerifyAccessRanges</a> with this modified <i>AccessRanges</i> array.

</li>
</ol>



## -see-also




<a href="https://msdn.microsoft.com/8c880eff-4b4c-439e-9239-f2343c1fe084">HwVidFindAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570302">VideoPortGetAccessRanges</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570310">VideoPortGetDeviceBase</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570377">VideoPortVerifyAccessRanges</a>
 

 

