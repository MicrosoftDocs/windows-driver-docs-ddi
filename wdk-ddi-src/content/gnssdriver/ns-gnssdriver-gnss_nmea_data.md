---
UID: NS:gnssdriver.GNSS_NMEA_DATA
title: GNSS_NMEA_DATA
author: windows-driver-content
description: This structure contains generic (non-parsed) NMEA data.
old-location: sensors\gnss_nmea_data.htm
old-project: sensors
ms.assetid: 6B890F85-0E77-41D2-B3B9-004F1882B6B5
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PGNSS_NMEA_DATA, GNSS_NMEA_DATA structure [Sensor Devices], gnssdriver/PGNSS_NMEA_DATA, GNSS_NMEA_DATA, sensors.gnss_nmea_data, *PGNSS_NMEA_DATA, gnssdriver/GNSS_NMEA_DATA, PGNSS_NMEA_DATA structure pointer [Sensor Devices]
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
-	GNSS_NMEA_DATA
product: Windows
targetos: Windows
req.typenames: *PGNSS_NMEA_DATA, GNSS_NMEA_DATA
---

# GNSS_NMEA_DATA structure


## -description


This structure contains generic (non-parsed) NMEA data.


## -syntax


````
typedef struct {
  ULONG Size;
  ULONG Version;
  CHAR  NmeaSentences[256];
} GNSS_NMEA_DATA, *PGNSS_NMEA_DATA;
````


## -struct-fields




### -field Size

Structure size.


### -field Version

Version number.


### -field NmeaSentences

 



#### - NmeaSentences[256]

Generic (non-parsed) NMEA data 

