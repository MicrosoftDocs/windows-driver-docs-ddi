---
UID: NS:gnssdriver.GNSS_FIXDATA_BASIC
title: GNSS_FIXDATA_BASIC
author: windows-driver-content
description: This structure defines basic position information.
old-location: sensors\gnss_fixdata_basic.htm
old-project: sensors
ms.assetid: D293366B-13FA-438E-BEBD-1F0EAA693400
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: gnssdriver/PGNSS_FIXDATA_BASIC, GNSS_FIXDATA_BASIC, *PGNSS_FIXDATA_BASIC, sensors.gnss_fixdata_basic, GNSS_FIXDATA_BASIC structure [Sensor Devices], gnssdriver/GNSS_FIXDATA_BASIC, PGNSS_FIXDATA_BASIC structure pointer [Sensor Devices], PGNSS_FIXDATA_BASIC
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
-	GNSS_FIXDATA_BASIC
product: Windows
targetos: Windows
req.typenames: "*PGNSS_FIXDATA_BASIC, GNSS_FIXDATA_BASIC"
---

# GNSS_FIXDATA_BASIC structure


## -description


This structure defines basic position information.


## -syntax


````
typedef struct {
  ULONG  Size;
  ULONG  Version;
  double Latitude;
  double Longitude;
  double Altitude;
  double Speed;
  double Heading;
} GNSS_FIXDATA_BASIC, *PGNSS_FIXDATA_BASIC;
````


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

