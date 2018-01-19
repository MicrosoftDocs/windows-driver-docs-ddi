---
UID: NS:ksmedia.tagKSCAMERA_EXTENDEDPROP_ROI_ISPCONTROLHEADER
title: tagKSCAMERA_EXTENDEDPROP_ROI_ISPCONTROLHEADER
author: windows-driver-content
description: This structure contains the header information for ROI ISP controls.
old-location: stream\kscamera_extendedprop_roi_ispcontrolheader.htm
old-project: stream
ms.assetid: F57B0E44-A6A1-4C43-83EE-8DF4A605C0D0
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: tagKSCAMERA_EXTENDEDPROP_ROI_ISPCONTROLHEADER, KSCAMERA_EXTENDEDPROP_ROI_ISPCONTROLHEADER, *PKSCAMERA_EXTENDEDPROP_ROI_ISPCONTROLHEADER
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
req.alt-api: KSCAMERA_EXTENDEDPROP_ROI_ISPCONTROLHEADER
req.alt-loc: Ksmedia.h
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
req.typenames: KSCAMERA_EXTENDEDPROP_ROI_ISPCONTROLHEADER, *PKSCAMERA_EXTENDEDPROP_ROI_ISPCONTROLHEADER
---

# tagKSCAMERA_EXTENDEDPROP_ROI_ISPCONTROLHEADER structure



## -description
This structure contains the header information for ROI ISP controls.



## -syntax

````
typedef struct tagKSCAMERA_EXTENDEDPROP_ROI_ISPCONTROLHEADER {
  ULONG     Size;
  ULONG     ControlCount;
  ULONGLONG Reserved;
} KSCAMERA_EXTENDEDPROP_ROI_ISPCONTROLHEADER, *PKSCAMERA_EXTENDEDPROP_ROI_ISPCONTROLHEADER;
````


## -struct-fields

### -field Size

The sum of this structure size, all <a href="..\ksmedia\ns-ksmedia-tagkscamera_extendedprop_roi_ispcontrol.md">KSCAMERA_EXTENDEDPROP_ROI_ISPCONTROL</a> structures, and all KSCAMERA_EXTENDEDPROP_ROI_RECTINFO structures that follow


### -field ControlCount

The number of ISP controls. If this value is 0, the ROI control will remove all ROIs previously configured. This effectively clears up all ROIs configured and resets the driver to the default ROI.


### -field Reserved

Reserved for future use.


## -remarks
