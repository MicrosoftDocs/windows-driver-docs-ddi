---
UID: NC:videoagp.PAGP_RELEASE_VIRTUAL
title: PAGP_RELEASE_VIRTUAL (videoagp.h)
description: The AgpReleaseVirtual function frees system memory reserved by a previous call to AgpReserveVirtual.
old-location: display\agpreleasevirtual.htm
tech.root: display
ms.assetid: 4e880b39-e0ee-4801-86b7-ffc06ed415ab
ms.date: 05/10/2018
keywords: ["PAGP_RELEASE_VIRTUAL callback function"]
ms.keywords: AgpReleaseVirtual, AgpReleaseVirtual callback function [Display Devices], PAGP_RELEASE_VIRTUAL, PAGP_RELEASE_VIRTUAL callback, VideoPort_Functions_4ea0bf12-5d18-4704-9efe-7d8a65a44f1f.xml, display.agpreleasevirtual, videoagp/AgpReleaseVirtual
f1_keywords:
 - "videoagp/AgpReleaseVirtual"
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- videoagp.h
api_name:
- AgpReleaseVirtual
product:
- Windows
targetos: Windows
req.typenames: 
---

# PAGP_RELEASE_VIRTUAL callback function


## -description


The <b>AgpReleaseVirtual</b> function frees system memory reserved by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/videoagp/nc-videoagp-pagp_reserve_virtual">AgpReserveVirtual</a>.


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param VirtualReserveContext [in]

Is the context handle that identifies the reserved virtual address range to be released. This context was obtained from <b>AgpReleaseVirtual</b>.


## -remarks



The miniport driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/videoagp/nc-videoagp-pagp_free_virtual">AgpFreeVirtual</a> to unmap all committed memory within the range identified by <b>VirtualReserveContext</b> before calling <b>AgpReleaseVirtual</b> to release it.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/videoagp/nc-videoagp-pagp_free_physical">AgpFreePhysical</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/videoagp/nc-videoagp-pagp_reserve_physical">AgpReservePhysical</a>
 

 

