---
UID: NS:gnssdriver.__unnamed_struct_17
title: GNSS_BREADCRUMB_V1 (gnssdriver.h)
description: This structure contains an individual breadcrumb. The order and types of the fields are designed to pack densely.
old-location: gnss\gnss_breadcrumb_v1.htm
tech.root: gnss
ms.assetid: BE1D09C4-8EC0-4BF3-A943-20EDD44F9CF1
ms.date: 02/15/2018
ms.keywords: "*PGNSS_BREADCRUMB_V1, GNSS_BREADCRUMB_V1, GNSS_BREADCRUMB_V1 structure [Sensor Devices], PGNSS_BREADCRUMB_V1, PGNSS_BREADCRUMB_V1 structure pointer [Sensor Devices], gnss.gnss_breadcrumb_v1, gnssdriver/GNSS_BREADCRUMB_V1, gnssdriver/PGNSS_BREADCRUMB_V1"
ms.topic: struct
f1_keywords:
 - "gnssdriver/GNSS_BREADCRUMB_V1"
req.header: gnssdriver.h
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
- gnssdriver.h
api_name:
- GNSS_BREADCRUMB_V1
product:
- Windows
targetos: Windows
req.typenames: GNSS_BREADCRUMB_V1, *PGNSS_BREADCRUMB_V1
---

# GNSS_BREADCRUMB_V1 structure


## -description


This structure contains an individual breadcrumb. The order and types of the fields are designed  to pack densely.


## -struct-fields




### -field FixTimeStamp

Contains the breadcrumb fix timestamp value.


### -field Latitude

Contains the breadcrumb longitude value at the time of the fix.


### -field Longitude

Contains the breadcrumb latitude at the time of the fix.


### -field HorizontalAccuracy

Contains the breadcrumb horizontal altitude value.


### -field Speed

Contains the speed value at the time of the breadcrumb fix.


### -field SpeedAccuracy

Contains the breadcrumb speed accuracy value.


### -field Altitude

Contains the breadcrumb altitude value at the time of the fix.


### -field AltitudeAccuracy

Contains the breadcrumb altitude accuracy value.


### -field Heading

Contains the breadcrumb heading value at the time of the fix.


### -field HeadingAccuracy

Contains the breadcrumb heading accuracy value.


### -field FixSuccess

A Boolean type that contains the fix success value.

