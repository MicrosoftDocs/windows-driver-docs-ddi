---
UID: NS:gnssdriver.GNSS_BREADCRUMB_V1
title: GNSS_BREADCRUMB_V1
author: windows-driver-content
description: This structure contains an individual breadcrumb. The order and types of the fields are designed to pack densely.
old-location: sensors\gnss_breadcrumb_v1.htm
old-project: sensors
ms.assetid: BE1D09C4-8EC0-4BF3-A943-20EDD44F9CF1
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: PGNSS_BREADCRUMB_V1, PGNSS_BREADCRUMB_V1 structure pointer [Sensor Devices], gnssdriver/PGNSS_BREADCRUMB_V1, GNSS_BREADCRUMB_V1, *PGNSS_BREADCRUMB_V1, gnssdriver/GNSS_BREADCRUMB_V1, sensors.gnss_breadcrumb_v1, GNSS_BREADCRUMB_V1 structure [Sensor Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	gnssdriver.h
apiname:
-	GNSS_BREADCRUMB_V1
product: Windows
targetos: Windows
req.typenames: GNSS_BREADCRUMB_V1, *PGNSS_BREADCRUMB_V1
---

# GNSS_BREADCRUMB_V1 structure


## -description


This structure contains an individual breadcrumb. The order and types of the fields are designed  to pack densely.


## -syntax


````
typedef struct {
  FILETIME       FixTimeStamp;
  double         Latitude;
  double         Longitude;
  ULONG          HorizontalAccuracy;
  unsigned short Speed;
  unsigned short SpeedAccuracy;
  short          Altitude;
  unsigned short AltitudeAccuracy;
  short          Heading;
  unsigned char  HeadingAccuracy;
  unsigned char  FixSuccess;
} GNSS_BREADCRUMB_V1, *PGNSS_BREADCRUMB_V1;
````


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

