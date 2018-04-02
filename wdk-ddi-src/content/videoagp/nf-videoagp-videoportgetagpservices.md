---
UID: NF:videoagp.VideoPortGetAgpServices
title: VideoPortGetAgpServices function
author: windows-driver-content
description: The VideoPortGetAgpServices function is obsolete and is supported only for backward compatibility with existing drivers.
old-location: display\videoportgetagpservices.htm
old-project: display
ms.assetid: 3b01831d-d429-4dc5-9b12-a0e1fc58634d
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: VideoPortGetAgpServices, VideoPortGetAgpServices function [Display Devices], VideoPort_Functions_498a8f06-f24e-4116-90df-30360fa111a1.xml, display.videoportgetagpservices, videoagp/VideoPortGetAgpServices
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: videoagp.h
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
-	VideoPortGetAgpServices
product: Windows
targetos: Windows
req.typenames: VP_SCATTER_GATHER_LIST, *PVP_SCATTER_GATHER_LIST
req.product: Windows 10 or later.
---

# VideoPortGetAgpServices function


## -description


The <b>VideoPortGetAgpServices</b> function is <b>obsolete</b> and is supported only for backward compatibility with existing drivers. In its place, driver writers should use <a href="https://msdn.microsoft.com/library/windows/hardware/ff570337">VideoPortQueryServices</a>.

<b>VideoPortGetAgpServices</b> returns a list of video port driver-implemented AGP service functions.


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param AgpServices [in]

Pointer to an uninitialized, miniport driver-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff570529">VIDEO_PORT_AGP_SERVICES</a> structure.


## -returns



<b>VideoPortGetAgpServices</b> returns <b>TRUE</b> after it successfully initializes the VIDEO_PORT_AGP_SERVICES structure to which <i>AgpServices</i> points; otherwise it returns <b>FALSE</b>.




## -remarks



PnP video miniport drivers that can use AGP should call <b>VideoPortGetAgpServices</b>.

The video port driver initializes the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570529">VIDEO_PORT_AGP_SERVICES</a> structure as follows:

<ul>
<li>
All function pointers are initialized to point to the corresponding video port driver-implemented AGP service functions.

</li>
<li>
The <b>AllocationLimit</b> field is initialized to the maximum amount of AGP memory that a miniport driver is allowed to commit, in bytes.

</li>
</ul>



## -see-also




<a href="https://msdn.microsoft.com/3c3a6936-7435-4a42-99e6-2c048613af23">AgpCommitPhysical</a>



<a href="https://msdn.microsoft.com/8a3e7fcd-d838-47ad-a42b-7eb070f81418">AgpCommitVirtual</a>



<a href="https://msdn.microsoft.com/bb0e3330-5601-47dd-afc6-94a70b42daaf">AgpFreePhysical</a>



<a href="https://msdn.microsoft.com/a6f689ab-8cf1-4207-af2b-30957500c190">AgpFreeVirtual</a>



<b>AgpReleasePhysical</b>



<a href="https://msdn.microsoft.com/4e880b39-e0ee-4801-86b7-ffc06ed415ab">AgpReleaseVirtual</a>



<a href="https://msdn.microsoft.com/b3e21c94-acd5-4767-8ba5-70b2dcfb2aaa">AgpReservePhysical</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570529">VIDEO_PORT_AGP_SERVICES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570337">VideoPortQueryServices</a>
 

 

