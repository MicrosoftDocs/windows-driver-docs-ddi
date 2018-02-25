---
UID: NS:d3dkmddi._DXGKARG_SETTIMINGSFROMVIDPN
title: "_DXGKARG_SETTIMINGSFROMVIDPN"
author: windows-driver-content
description: Used to hold the arguments for DXGKDDI_SETTIMINGSFROMVIDPN.
old-location: display\dxgkarg_settimingsfromvidpn.htm
old-project: display
ms.assetid: 14D652C4-9812-481E-8E69-A6D7923F01A3
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , *, *IN_OUT_PDXGKARG_SETTIMINGSFROMVIDPN, ,, A, D, DXGKARG_SETTIMINGSFROMVIDPN, DXGKARG_SETTIMINGSFROMVIDPN structure [Display Devices], E, F, G, I, K, M, N, O, P, PDXGKARG_SETTIMINGSFROMVIDPN, PDXGKARG_SETTIMINGSFROMVIDPN structure pointer [Display Devices], R, S, T, U, V, X, _, _DXGKARG_SETTIMINGSFROMVIDPN, d3dkmddi/DXGKARG_SETTIMINGSFROMVIDPN, d3dkmddi/PDXGKARG_SETTIMINGSFROMVIDPN, display.dxgkarg_settimingsfromvidpn"
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGKARG_SETTIMINGSFROMVIDPN
product: Windows
targetos: Windows
req.typenames: DXGKARG_SETTIMINGSFROMVIDPN
---

# _DXGKARG_SETTIMINGSFROMVIDPN structure


## -description


Used to hold the arguments for <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_settimingsfromvidpn.md">DXGKDDI_SETTIMINGSFROMVIDPN</a>.


## -syntax


````
typedef struct _DXGKARG_SETTIMINGSFROMVIDPN {
  D3DKMDT_HVIDPN            hFunctionalVidPn;
  DXGK_SET_TIMING_FLAGS     SetFlags;
  PDXGK_SET_TIMING_RESULTS  pResultsFlags;
  UINT                      PathCount;
  DXGK_SET_TIMING_PATH_INFO *pSetTimingPathInfo;
} DXGKARG_SETTIMINGSFROMVIDPN, *PDXGKARG_SETTIMINGSFROMVIDPN;
````


## -struct-fields




### -field hFunctionalVidPn

Handle to a functional VidPn which describes the display configuration the OS is attempting to apply.


### -field SetFlags

 A DXGK_SET_TIMING_FLAGS structure that requests specific actions from the driver on the SetTimingsFromVidPn call.


### -field pResultsFlags

Pointer to a DXGK_SET_TIMING_RESULTS structure that the driver should use to report overall results from the SetTimingsFromVidPn call.


### -field PathCount

Number of pointers in the array pointed to by pSetTimingPathInfo.


### -field pSetTimingPathInfo

An array of pointers to DXGK_SET_TIMING_PATH_INFO structures that specify per path details of the timings to be set. It also allows feedback from the driver on additional work the OS needs to do either before the timings changes can be made, or after changes are complete.

