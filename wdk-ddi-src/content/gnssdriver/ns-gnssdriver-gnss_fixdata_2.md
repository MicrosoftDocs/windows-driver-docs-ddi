---
UID: NS:gnssdriver.__unnamed_struct_18
title: GNSS_FIXDATA_2 (gnssdriver.h)
ms.date: 04/05/2021
targetos: Windows
tech.root: gnss
description: The GNSS_FIXDATA_2 structure defines the specific data elements associated with a GNSS fix returned from the driver.
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
req.typenames: GNSS_FIXDATA_2, *PGNSS_FIXDATA_2
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - gnssdriver.h
api_name:
 - PGNSS_FIXDATA_2
 - GNSS_FIXDATA_2
f1_keywords:
 - PGNSS_FIXDATA_2
 - gnssdriver/PGNSS_FIXDATA_2
 - GNSS_FIXDATA_2
 - gnssdriver/GNSS_FIXDATA_2
dev_langs:
 - c++
---

## -description

The **GNSS_FIXDATA_2** structure defines the specific data elements associated with a GNSS fix returned from the driver.

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

## -remarks

## -see-also
