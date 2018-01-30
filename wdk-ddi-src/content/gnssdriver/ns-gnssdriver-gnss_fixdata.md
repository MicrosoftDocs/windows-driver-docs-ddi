---
UID: NS:gnssdriver.GNSS_FIXDATA
title: GNSS_FIXDATA
author: windows-driver-content
description: This structure defines the specific data elements associated with a GNSS fix returned from the driver.
old-location: sensors\gnss_fixdata.htm
old-project: sensors
ms.assetid: 2939F01A-2F1C-4434-BAE1-59F1F320BD44
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: GNSS_FIXDATA, gnssdriver/GNSS_FIXDATA, gnssdriver/PGNSS_FIXDATA, sensors.gnss_fixdata, PGNSS_FIXDATA structure pointer [Sensor Devices], *PGNSS_FIXDATA, GNSS_FIXDATA structure [Sensor Devices], PGNSS_FIXDATA
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
-	GNSS_FIXDATA
product: Windows
targetos: Windows
req.typenames: GNSS_FIXDATA, *PGNSS_FIXDATA
---

# GNSS_FIXDATA structure


## -description


This structure defines the specific data elements associated with a GNSS fix returned from the driver.


## -syntax


````
typedef struct {
  ULONG                  Size;
  ULONG                  Version;
  ULONG                  FixSessionID;
  FILETIME               FixTimeStamp;
  BOOL                   IsFinalFix;
  NTSTATUS               FixStatus;
  ULONG                  FixLevelOfDetails;
  GNSS_FIXDATA_BASIC     BasicData;
  GNSS_FIXDATA_ACCURACY  AccuracyData;
  GNSS_FIXDATA_SATELLITE SatelliteData;
} GNSS_FIXDATA, *PGNSS_FIXDATA;
````


## -struct-fields




### -field Size

Structure size.


### -field Version

Version number.


### -field FixSessionID

ID of the fix session that generated this fix.

The GNSS driver populates this field so that the GNSS adapter can correlate the fix data with the original start fix request.


### -field FixTimeStamp

Timestamp when the fix is generated.

This should be the time obtained from the satellites measurements.


### -field IsFinalFix

Boolean value indicating whether this is a final fix or not.

A value of FALSE implies this is an intermediate fix and a final fix is forthcoming.


### -field FixStatus

An NTSTATUS value indicating whether this fix contains a valid fix, or if the GNSS engine/driver encountered any error in getting the fix.

Unless this value indicates success, the basic fix data element of this structure should not be relied on. Satellite and mode data elements may still be valid.


### -field FixLevelOfDetails

A bitmask containing the GNSS_FIXDETAIL_* bits that determine which members of this structure are populated by the GNSS driver. 


### -field BasicData

This element contains the basic fix data fix when FixLevelofDetails field has GNSS_FIXDETAIL_BASIC bit set.

Unless explicitly indicated in the fix session parameter, the GNSS driver is recommended to always populate this element.


### -field AccuracyData

This element contains the accuracy-related data when FixLevelofDetails field has GNSS_FIXDETAIL_ACCURACY bit set.


### -field SatelliteData

This element contains the satellite-related data when FixLevelofDetails field has GNSS_FIXDETAIL_SATELLITE bit set.

