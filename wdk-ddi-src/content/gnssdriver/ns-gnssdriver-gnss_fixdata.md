---
UID: NS:gnssdriver.__unnamed_struct_14
title: GNSS_FIXDATA
author: windows-driver-content
description: This structure defines the specific data elements associated with a GNSS fix returned from the driver.
old-location: gnss\gnss_fixdata.htm
tech.root: gnss
ms.assetid: 2939F01A-2F1C-4434-BAE1-59F1F320BD44
ms.date: 02/15/2018
ms.keywords: "*PGNSS_FIXDATA, GNSS_FIXDATA, GNSS_FIXDATA structure [Sensor Devices], PGNSS_FIXDATA, PGNSS_FIXDATA structure pointer [Sensor Devices], gnss.gnss_fixdata, gnssdriver/GNSS_FIXDATA, gnssdriver/PGNSS_FIXDATA"
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
-	GNSS_FIXDATA
product:
- Windows
targetos: Windows
req.typenames: GNSS_FIXDATA, *PGNSS_FIXDATA
---

# GNSS_FIXDATA structure


## -description


This structure defines the specific data elements associated with a GNSS fix returned from the driver.


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

