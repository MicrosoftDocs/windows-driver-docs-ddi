---
UID: NS:gnssdriver.GNSS_FIXDATA_ACCURACY
title: GNSS_FIXDATA_ACCURACY
author: windows-driver-content
description: This structure defines the accuracy details of a fix.
old-location: sensors\gnss_fixdata_accuracy.htm
old-project: sensors
ms.assetid: 3C08FE5D-1385-4FE3-98C9-9FC530C6C755
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: gnssdriver/PGNSS_FIXDATA_ACCURACY, *PGNSS_FIXDATA_ACCURACY, gnssdriver/GNSS_FIXDATA_ACCURACY, GNSS_FIXDATA_ACCURACY structure [Sensor Devices], GNSS_FIXDATA_ACCURACY, PGNSS_FIXDATA_ACCURACY, PGNSS_FIXDATA_ACCURACY structure pointer [Sensor Devices], sensors.gnss_fixdata_accuracy
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




#### - Size

Structure size.


#### - Version

Version number.


#### - HorizontalAccuracy

Accuracy reported with 95% confidence.


#### - HorizontalErrorMajorAxis

Horizontal uncertainty ellipse semi-major axis with  95% confidence accuracy.


#### - HorizontalErrorMinorAxis

Horizontal uncertainty ellipse semi-minor axis with  95% confidence accuracy.


#### - HorizontalErrorAngle

Horizontal uncertainty ellipse orientation angle with  95% confidence accuracy.


#### - HeadingAccuracy

Reserved, do not use.


#### - AltitudeAccuracy

Reserved, do not use.


#### - SpeedAccuracy

Reserved, do not use.


#### - HorizontalConfidence

Reserved, do not use.


#### - HeadingConfidence

Reserved, do not use.


#### - AltitudeConfidence

Reserved, do not use.


#### - SpeedConfidence

Reserved, do not use.


#### - PositionDilutionOfPrecision

Position dilution of precision (PDOP).

Satellite-based positions with a dilution of precision (DOP) value of 0 or a DOP value higher than 10 may be filtered by the GNSS adapter.


#### - HorizontalDilutionOfPrecision

Horizontal dilution of precision (HDOP).


#### - VerticalDilutionOfPrecision

Vertical dilution of precision (VDOP).

