---
UID: NC:videoagp.PAGP_RELEASE_PHYSICAL
title: PAGP_RELEASE_PHYSICAL (videoagp.h)
description: The AgpReleasePhysical function frees a physical address range reserved by a previous call to AgpReservePhysical.
old-location: display\agpreleasephysical.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["PAGP_RELEASE_PHYSICAL callback function"]
ms.keywords: AgpReleasePhysical, AgpReleasePhysical callback function [Display Devices], PAGP_RELEASE_PHYSICAL, PAGP_RELEASE_PHYSICAL callback, VideoPort_Functions_427923a7-3205-41a7-a470-dbc7d531e47f.xml, display.agpreleasephysical, videoagp/AgpReleasePhysical
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PAGP_RELEASE_PHYSICAL
 - videoagp/PAGP_RELEASE_PHYSICAL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - videoagp.h
api_name:
 - AgpReleasePhysical
---

# PAGP_RELEASE_PHYSICAL callback function


## -description

The <b>AgpReleasePhysical</b> function frees a physical address range reserved by a previous call to <a href="/windows-hardware/drivers/ddi/videoagp/nc-videoagp-pagp_reserve_physical">AgpReservePhysical</a>.

## -parameters

### -param HwDeviceExtension 

[in]
Pointer to the miniport driver's device extension.

### -param PhysicalReserveContext 

[in]
Is the context handle that identifies the reserved physical address range to be released. This context was obtained from <a href="/windows-hardware/drivers/ddi/videoagp/nc-videoagp-pagp_reserve_physical">AgpReservePhysical</a>.

## -remarks

The miniport driver must call <a href="/windows-hardware/drivers/ddi/videoagp/nc-videoagp-pagp_free_physical">AgpFreePhysical</a> to unmap all committed memory within the address range identified by <b>PhysicalReserveContext</b> before calling <b>AgpReleasePhysical</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/videoagp/nc-videoagp-pagp_free_physical">AgpFreePhysical</a>



<a href="/windows-hardware/drivers/ddi/videoagp/nc-videoagp-pagp_reserve_physical">AgpReservePhysical</a>
