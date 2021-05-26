---
UID: NS:gnssdriver.__unnamed_struct_14
tech.root: gnss
title: GNSS_FIXDATA_ACCURACY_2
ms.date: 04/05/2021
targetos: Windows
description: The GNSS_FIXDATA_ACCURACY_2 structure defines the accuracy details of a fix.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: gnssdriver.h
req.include-header: Gnssdriver.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt:
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: GNSS_FIXDATA_ACCURACY_2, *PGNSS_FIXDATA_ACCURACY_2
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - gnssdriver.h
api_name:
 - PGNSS_FIXDATA_ACCURACY_2
 - GNSS_FIXDATA_ACCURACY_2
f1_keywords:
 - PGNSS_FIXDATA_ACCURACY_2
 - gnssdriver/PGNSS_FIXDATA_ACCURACY_2
 - GNSS_FIXDATA_ACCURACY_2
 - gnssdriver/GNSS_FIXDATA_ACCURACY_2
dev_langs:
 - c++
---

## -description

The **GNSS_FIXDATA_ACCURACY_2** structure defines the accuracy details of a fix.

## -struct-fields

### -field Size

Structure size.

### -field Version

Version number.

### -field HorizontalAccuracy

Accuracy reported with 95% confidence.

### -field HorizontalErrorMajorAxis

Horizontal uncertainty ellipse semi-major axis with 95% confidence accuracy.

### -field HorizontalErrorMinorAxis

Horizontal uncertainty ellipse semi-minor axis with 95% confidence accuracy.

### -field HorizontalErrorAngle

Horizontal uncertainty ellipse orientation angle with 95% confidence accuracy.

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

### -field HorizontalDilutionOfPrecision

Horizontal dilution of precision (HDOP).

### -field VerticalDilutionOfPrecision

Vertical dilution of precision (VDOP).

### -field GeometricDilutionOfPrecision

Geometric dilution of precision.

### -field TimeDilutionOfPrecision

Time dilution of precision.

## -remarks

## -see-also
