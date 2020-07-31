---
UID: NS:d3dkmddi._DXGK_SET_TIMING_RESULTS
title: _DXGK_SET_TIMING_RESULTS (d3dkmddi.h)
description: Structure to report result flags from the SetTiming call which apply to the complete call rather than individual paths.
old-location: display\dxgk_set_timing_results.htm
ms.assetid: EA5C845B-76FD-40AD-B4E8-78601CA847CE
ms.date: 05/10/2018
keywords: ["_DXGK_SET_TIMING_RESULTS structure"]
ms.keywords: "*PDXGK_SET_TIMING_RESULTS, DXGK_SET_TIMING_RESULTS, DXGK_SET_TIMING_RESULTS structure [Display Devices], PDXGK_SET_TIMING_RESULTS, PDXGK_SET_TIMING_RESULTS structure pointer [Display Devices], _DXGK_SET_TIMING_RESULTS, d3dkmddi/DXGK_SET_TIMING_RESULTS, d3dkmddi/PDXGK_SET_TIMING_RESULTS, display.dxgk_set_timing_results"
f1_keywords:
 - "d3dkmddi/DXGK_SET_TIMING_RESULTS"
 - "DXGK_SET_TIMING_RESULTS"
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Windows
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmddi.h
api_name:
- DXGK_SET_TIMING_RESULTS
targetos: Windows
tech.root: display
req.typenames: DXGK_SET_TIMING_RESULTS, *PDXGK_SET_TIMING_RESULTS
---

# _DXGK_SET_TIMING_RESULTS structure


## -description


Structure to report result flags from the SetTiming call which apply to the complete call rather than individual paths.


## -struct-fields




### -field ConnectionStatusChanges

If set, indicates that one or more connector status changes were detected in the course of this call so the OS needs to call DxgkDdiQueryConnectionStatus to catch up with all changes and to resync with the current state.  

<div class="alert"><b>Note</b>  This flag is intended to indicate to the OS that a change in available displays has occurred so TargetStatus* and MonitorStatus* changes should cause the driver to set the flag whereas LinkConfiguration* changes should be reported but should not cause the flag to be set.  Any update to an active path requires that a LinkConfiguration* change be reported so that the status of the change can be distinguished from previous changes with the same result so including these changes in the flag would not provide useful information.</div>
<div> </div>

### -field Reserved

This value is reserved for system use.


### -field Value

UINT used to operate on the combined bit-fields.

