---
UID: NS:d3dkmddi._DXGKARG_SETTIMINGSFROMVIDPN
title: "_DXGKARG_SETTIMINGSFROMVIDPN"
author: windows-driver-content
description: Used to hold the arguments for DXGKDDI_SETTIMINGSFROMVIDPN.
old-location: display\dxgkarg_settimingsfromvidpn.htm
ms.assetid: 14D652C4-9812-481E-8E69-A6D7923F01A3
ms.date: 5/10/2018
ms.keywords: "*IN_OUT_PDXGKARG_SETTIMINGSFROMVIDPN, DXGKARG_SETTIMINGSFROMVIDPN, DXGKARG_SETTIMINGSFROMVIDPN structure [Display Devices], PDXGKARG_SETTIMINGSFROMVIDPN, PDXGKARG_SETTIMINGSFROMVIDPN structure pointer [Display Devices], _DXGKARG_SETTIMINGSFROMVIDPN, d3dkmddi/DXGKARG_SETTIMINGSFROMVIDPN, d3dkmddi/PDXGKARG_SETTIMINGSFROMVIDPN, display.dxgkarg_settimingsfromvidpn"
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGKARG_SETTIMINGSFROMVIDPN
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGKARG_SETTIMINGSFROMVIDPN
---

# _DXGKARG_SETTIMINGSFROMVIDPN structure


## -description


Used to hold the arguments for <a href="https://msdn.microsoft.com/7E991251-1738-41AD-83D6-60DD7E183D68">DXGKDDI_SETTIMINGSFROMVIDPN</a>.


## -struct-fields




### -field hFunctionalVidPn

A handle to a D3DKMDT_HVIDPN that represents a functional VidPn which describes the display configuration the OS is attempting to apply.

The D3DKMDT_HVIDPN data type is defined in <i>D3dkmdt.h</i>. 

### -field SetFlags

 A [DXGK_SET_TIMING_FLAGS](ns-d3dkmddi-_dxgk_set_timing_flags.md) structure that requests specific actions from the driver on the SetTimingsFromVidPn call.


### -field pResultsFlags

Pointer to a [DXGK_SET_TIMING_RESULTS](ns-d3dkmddi-_dxgk_set_timing_results.md) structure that the driver should use to report overall results from the [SetTimingsFromVidPn](nc-d3dkmddi-dxgkddi_settimingsfromvidpn.md) call.


### -field PathCount

Number of pointers in the array pointed to by **pSetTimingPathInfo**.


### -field pSetTimingPathInfo

An array of pointers to [DXGK_SET_TIMING_PATH_INFO](ns-d3dkmddi-_dxgk_set_timing_path_info.md) structures that specify per path details of the timings to be set. It also allows feedback from the driver on additional work the OS needs to do either before the timings changes can be made, or after changes are complete.

