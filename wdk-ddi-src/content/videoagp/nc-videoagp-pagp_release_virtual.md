---
UID: NC:videoagp.PAGP_RELEASE_VIRTUAL
title: PAGP_RELEASE_VIRTUAL
author: windows-driver-content
description: The AgpReleaseVirtual function frees system memory reserved by a previous call to AgpReserveVirtual.
old-location: display\agpreleasevirtual.htm
old-project: display
ms.assetid: 4e880b39-e0ee-4801-86b7-ffc06ed415ab
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: AgpReleaseVirtual, AgpReleaseVirtual callback function [Display Devices], PAGP_RELEASE_VIRTUAL, VideoPort_Functions_4ea0bf12-5d18-4704-9efe-7d8a65a44f1f.xml, display.agpreleasevirtual, videoagp/AgpReleaseVirtual
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	videoagp.h
api_name:
-	AgpReleaseVirtual
product: Windows
targetos: Windows
req.typenames: VP_SCATTER_GATHER_LIST, *PVP_SCATTER_GATHER_LIST
req.product: Windows 10 or later.
---

# PAGP_RELEASE_VIRTUAL callback


## -description


The <b>AgpReleaseVirtual</b> function frees system memory reserved by a previous call to <a href="https://msdn.microsoft.com/966dfc6c-6830-4872-b411-2801e3a4b753">AgpReserveVirtual</a>.


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param VirtualReserveContext [in]

Is the context handle that identifies the reserved virtual address range to be released. This context was obtained from <b>AgpReleaseVirtual</b>.


## -returns



None




## -remarks



The miniport driver must call <a href="https://msdn.microsoft.com/a6f689ab-8cf1-4207-af2b-30957500c190">AgpFreeVirtual</a> to unmap all committed memory within the range identified by <b>VirtualReserveContext</b> before calling <b>AgpReleaseVirtual</b> to release it.




## -see-also




<a href="https://msdn.microsoft.com/bb0e3330-5601-47dd-afc6-94a70b42daaf">AgpFreePhysical</a>



<a href="https://msdn.microsoft.com/b3e21c94-acd5-4767-8ba5-70b2dcfb2aaa">AgpReservePhysical</a>
 

 

