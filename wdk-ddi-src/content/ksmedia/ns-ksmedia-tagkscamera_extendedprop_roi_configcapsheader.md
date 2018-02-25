---
UID: NS:ksmedia.tagKSCAMERA_EXTENDEDPROP_ROI_CONFIGCAPSHEADER
title: tagKSCAMERA_EXTENDEDPROP_ROI_CONFIGCAPSHEADER
author: windows-driver-content
description: This structure contains the header information for ROI capabilities.
old-location: stream\kscamera_extendedprop_roi_configcapsheader.htm
old-project: stream
ms.assetid: E915BF71-F29C-440B-9A56-50389AA8A9CF
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , *, *PKSCAMERA_EXTENDEDPROP_ROI_CONFIGCAPSHEADER, ,, A, C, D, E, F, G, H, I, K, KSCAMERA_EXTENDEDPROP_ROI_CONFIGCAPSHEADER, KSCAMERA_EXTENDEDPROP_ROI_CONFIGCAPSHEADER structure [Streaming Media Devices], M, N, O, P, PKSCAMERA_EXTENDEDPROP_ROI_CONFIGCAPSHEADER, PKSCAMERA_EXTENDEDPROP_ROI_CONFIGCAPSHEADER structure pointer [Streaming Media Devices], R, S, T, X, _, a, g, ksmedia/KSCAMERA_EXTENDEDPROP_ROI_CONFIGCAPSHEADER, ksmedia/PKSCAMERA_EXTENDEDPROP_ROI_CONFIGCAPSHEADER, stream.kscamera_extendedprop_roi_configcapsheader, t, tagKSCAMERA_EXTENDEDPROP_ROI_CONFIGCAPSHEADER"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ksmedia.h
apiname:
-	KSCAMERA_EXTENDEDPROP_ROI_CONFIGCAPSHEADER
product: Windows
targetos: Windows
req.typenames: KSCAMERA_EXTENDEDPROP_ROI_CONFIGCAPSHEADER, *PKSCAMERA_EXTENDEDPROP_ROI_CONFIGCAPSHEADER
---

# tagKSCAMERA_EXTENDEDPROP_ROI_CONFIGCAPSHEADER structure


## -description


This structure contains the header information for ROI capabilities.


## -syntax


````
typedef struct tagKSCAMERA_EXTENDEDPROP_ROI_CONFIGCAPSHEADER {
  ULONG     Size;
  ULONG     ConfigCapCount;
  ULONGLONG Reserved;
} KSCAMERA_EXTENDEDPROP_ROI_CONFIGCAPSHEADER, *PKSCAMERA_EXTENDEDPROP_ROI_CONFIGCAPSHEADER;
````


## -struct-fields




### -field Size

The size of this header and all <a href="..\ksmedia\ns-ksmedia-tagkscamera_extendedprop_roi_configcaps.md">KSCAMERA_EXTENDEDPROP_ROI_CONFIGCAPS</a> structures that follow.


### -field ConfigCapCount

Contains the number of <b>KSCAMERA_EXTENDEDPROP_ROI_CONFIGCAPS</b> structures that follow.


### -field Reserved

Reserved for future use.

