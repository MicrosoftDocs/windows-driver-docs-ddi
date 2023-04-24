---
UID: NS:gnssdriver.GNSS_FIXDATA_BASIC_2
title: GNSS_FIXDATA_BASIC_2 (gnssdriver.h)
ms.date: 04/05/2021
targetos: Windows
tech.root: gnss
description: The GNSS_FIXDATA_BASIC_2 structure defines basic position information.
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
req.typenames: GNSS_FIXDATA_BASIC_2, *PGNSS_FIXDATA_BASIC_2
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - gnssdriver.h
api_name:
 - PGNSS_FIXDATA_BASIC_2
 - GNSS_FIXDATA_BASIC_2
f1_keywords:
 - PGNSS_FIXDATA_BASIC_2
 - gnssdriver/PGNSS_FIXDATA_BASIC_2
 - GNSS_FIXDATA_BASIC_2
 - gnssdriver/GNSS_FIXDATA_BASIC_2
dev_langs:
 - c++
---

## -description

The **GNSS_FIXDATA_BASIC_2** structure defines basic position information.

## -struct-fields

### -field Size

Structure size.

### -field Version

Version number.

### -field Latitude

Latitude value. Valid range is -180.0 to + 180.0. NaN indicates unavailable.

### -field Longitude

Longitude value. Valid range is -90.0 to + 90.0. NaN indicates unavailable.

### -field Altitude

Altitude value in meters (in relation to sea level). NaN indicates unavailable.

### -field Speed

Speed in meters per second. Zero or positive value. NaN indicates unavailable.

### -field Heading

Heading/direction in degrees. Valid range is 0 to 360. Zero indicates true north. NaN indicates unavailable.

### -field AltitudeEllipsoid

## -remarks

## -see-also

