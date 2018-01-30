---
UID: NE:gnssdriver.GNSS_GEOREGIONTYPE
title: GNSS_GEOREGIONTYPE
author: windows-driver-content
description: This enumeration is used for defining a geographical shape. A shape is used to define a geofence. Windows 10 currently only supports circular geofences.
old-location: sensors\gnss_georegiontype.htm
old-project: sensors
ms.assetid: 736A1D63-A96E-4E29-ADFD-F441AC4757C6
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: GNSS_GeoRegion_Circle, GNSS_GEOREGIONTYPE enumeration [Sensor Devices], gnssdriver/GNSS_GeoRegion_Circle, gnssdriver/GNSS_GEOREGIONTYPE, GNSS_GEOREGIONTYPE, sensors.gnss_georegiontype
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	gnssdriver.h
apiname:
-	GNSS_GEOREGIONTYPE
product: Windows
targetos: Windows
req.typenames: GNSS_GEOREGIONTYPE
---

# GNSS_GEOREGIONTYPE enumeration


## -description


This enumeration is used for defining a geographical shape. A shape is used to define a geofence. Windows 10 currently only supports circular geofences.


## -syntax


````
typedef enum  { 
  GNSS_GeoRegion_Circle  = 0x01
} GNSS_GEOREGIONTYPE;
````


## -enum-fields




### -field GNSS_GeoRegion_Circle

Defines a circular geofence.

