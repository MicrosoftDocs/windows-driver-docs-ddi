---
UID: NS:gnssdriver.GNSS_FIXDATA_ACCURACY
title: GNSS_FIXDATA_ACCURACY
author: windows-driver-content
description: This structure defines the accuracy details of a fix.
old-location: sensors\gnss_fixdata_accuracy.htm
old-project: sensors
ms.assetid: 3C08FE5D-1385-4FE3-98C9-9FC530C6C755
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: "*PGNSS_FIXDATA_ACCURACY, GNSS_FIXDATA_ACCURACY, GNSS_FIXDATA_ACCURACY structure [Sensor Devices], PGNSS_FIXDATA_ACCURACY, PGNSS_FIXDATA_ACCURACY structure pointer [Sensor Devices], gnssdriver/GNSS_FIXDATA_ACCURACY, gnssdriver/PGNSS_FIXDATA_ACCURACY, sensors.gnss_fixdata_accuracy"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	gnssdriver.h
api_name:
-	GNSS_FIXDATA_ACCURACY
product: Windows
targetos: Windows
req.typenames: GNSS_FIXDATA_ACCURACY, *PGNSS_FIXDATA_ACCURACY
---

# GNSS_FIXDATA_ACCURACY structure


## -description


This structure defines the accuracy details of a fix.


## -syntax


````
typedef struct {
  ULONG Size;
  ULONG Version;
  ULONG HorizontalAccuracy;
  ULONG HorizontalErrorMajorAxis;
  ULONG HorizontalErrorMinorAxis;
  ULONG HorizontalErrorAngle;
  ULONG HeadingAccuracy;
  ULONG AltitudeAccuracy;
  ULONG SpeedAccuracy;
  ULONG HorizontalConfidence;
  ULONG HeadingConfidence;
  ULONG AltitudeConfidence;
  ULONG SpeedConfidence;
  float PositionDilutionOfPrecision;
  float HorizontalDilutionOfPrecision;
  float VerticalDilutionOfPrecision;
} GNSS_FIXDATA_ACCURACY, *PGNSS_FIXDATA_ACCURACY;
````


## -struct-fields




### -field Size

Structure size.


### -field Version

Version number.


### -field HorizontalAccuracy

Accuracy reported with 95% confidence.


### -field HorizontalErrorMajorAxis

Horizontal uncertainty ellipse semi-major axis with  95% confidence accuracy.


### -field HorizontalErrorMinorAxis

Horizontal uncertainty ellipse semi-minor axis with  95% confidence accuracy.


### -field HorizontalErrorAngle

Horizontal uncertainty ellipse orientation angle with  95% confidence accuracy.


### -field HeadingAccuracy

Reserved, do not use.


### -field AltitudeAccuracy

Reserved, do not use.


### -field SpeedAccuracy

Reserved, do not use.


### -field HorizontalConfidence

Reserved, do not use.


### -field HeadingConfidence

Reserved, do not use.


### -field AltitudeConfidence

Reserved, do not use.


### -field SpeedConfidence

Reserved, do not use.


### -field PositionDilutionOfPrecision

Position dilution of precision (PDOP).

Satellite-based positions with a dilution of precision (DOP) value of 0 or a DOP value higher than 10 may be filtered by the GNSS adapter.


### -field HorizontalDilutionOfPrecision

Horizontal dilution of precision (HDOP).


### -field VerticalDilutionOfPrecision

Vertical dilution of precision (VDOP).

