---
UID: NC:videoagp.PAGP_FREE_PHYSICAL
title: PAGP_FREE_PHYSICAL
author: windows-driver-content
description: The AgpFreePhysical function frees system memory that was committed by a previous call to AgpCommitPhysical.
old-location: display\agpfreephysical.htm
old-project: display
ms.assetid: bb0e3330-5601-47dd-afc6-94a70b42daaf
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: AgpFreePhysical, AgpFreePhysical callback function [Display Devices], PAGP_FREE_PHYSICAL, VideoPort_Functions_cc6360b5-12f9-4c49-bb06-d86ada229b9e.xml, display.agpfreephysical, videoagp/AgpFreePhysical
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
-	AgpFreePhysical
product: Windows
targetos: Windows
req.typenames: VP_SCATTER_GATHER_LIST, *PVP_SCATTER_GATHER_LIST
req.product: Windows 10 or later.
---

# PAGP_FREE_PHYSICAL callback


## -description


The <b>AgpFreePhysical</b> function frees system memory that was committed by a previous call to <a href="..\videoagp\nc-videoagp-pagp_commit_physical.md">AgpCommitPhysical</a>.


## -prototype


````
PAGP_FREE_PHYSICAL AgpFreePhysical;

VOID APIENTRY AgpFreePhysical(
  _In_ PVOID HwDeviceExtension,
  _In_ PVOID PhysicalReserveContext,
  _In_ ULONG Pages,
  _In_ ULONG Offset
)
{ ... }
````


## -parameters




### -param HwDeviceExtension [in]

Pointer to the device extension of the miniport driver.


### -param PhysicalReserveContext [in]

Identifies a reserved physical address range. This context handle was obtained from <a href="..\videoagp\nc-videoagp-pagp_reserve_physical.md">AgpReservePhysical</a>.


### -param Pages [in]

Specifies the number of pages of system memory that the video port driver should unmap.


### -param Offset [in]

Specifies the page offset into the reserved physical address range identified by <b>PhysicalReserveContext</b> that indicates the actual base address at which to unmap system memory.


## -returns



None




## -remarks



When a miniport driver calls <b>AgpFreePhysical</b>, <b>Pages</b> pages of physical memory are unlocked and unmapped from the AGP-decodable physical address range. This range begins <b>Offset</b> pages into the range identified by <b>PhysicalReserveContext</b>. The miniport driver must specify that the exact offset and number of pages be freed as were committed in a prior call to <a href="..\videoagp\nc-videoagp-pagp_commit_physical.md">AgpCommitPhysical</a>.




## -see-also

<a href="..\videoagp\nc-videoagp-pagp_commit_physical.md">AgpCommitPhysical</a>



<a href="..\videoagp\nc-videoagp-pagp_release_physical.md">AgpReleasePhysical</a>



 

 


