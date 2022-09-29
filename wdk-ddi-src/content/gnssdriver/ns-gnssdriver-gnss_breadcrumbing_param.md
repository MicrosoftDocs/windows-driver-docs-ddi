---
UID: NS:gnssdriver.__unnamed_struct_19
title: GNSS_BREADCRUMBING_PARAM (gnssdriver.h)
description: The GNSS_BREADCRUMBING_PARAM structure contains the configuration passed into the start of breadcrumbing via IOCTL_GNSS_START_BREADCRUMBING.
tech.root: gnss
ms.date: 06/17/2022
keywords: ["GNSS_BREADCRUMBING_PARAM structure"]
ms.keywords: "*PGNSS_BREADCRUMBING_PARAM, GNSS_BREADCRUMBING_PARAM, GNSS_BREADCRUMBING_PARAM structure [Sensor Devices], PGNSS_BREADCRUMBING_PARAM, PGNSS_BREADCRUMBING_PARAM structure pointer [Sensor Devices], gnss.gnss_breadcrumbing_param, gnssdriver/GNSS_BREADCRUMBING_PARAM, gnssdriver/PGNSS_BREADCRUMBING_PARAM"
req.header: gnssdriver.h
req.include-header: Gnssdriver.h
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
targetos: Windows
req.typenames: GNSS_BREADCRUMBING_PARAM, *PGNSS_BREADCRUMBING_PARAM
f1_keywords:
 - PGNSS_BREADCRUMBING_PARAM
 - gnssdriver/PGNSS_BREADCRUMBING_PARAM
 - GNSS_BREADCRUMBING_PARAM
 - gnssdriver/GNSS_BREADCRUMBING_PARAM
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - gnssdriver.h
api_name:
 - PGNSS_BREADCRUMBING_PARAM
 - GNSS_BREADCRUMBING_PARAM
---

## -description

The **GNSS_BREADCRUMBING_PARAM** structure contains the configuration passed into the start of breadcrumbing via [IOCTL_GNSS_START_BREADCRUMBING](./ni-gnssdriver-ioctl_gnss_start_breadcrumbing.md).

## -struct-fields

### -field Size

Structure size.

### -field Version

Version number.

### -field MaximumHorizontalUncertainty

Contains the maximum horizontal uncertainty value. Any fix with an error radius larger than this value shall not be recorded.

### -field MinDistanceBetweenFixes

Contains the minimum distance between fixes. Only record a fix if the center of it is at least as far apart as this value from center of the last fix, using a Haversine distance calculation.

### -field MaximumErrorTimeoutMs

Contains the maximum error timeout in milliseconds. If the location of the device is unknown for this duration, an error must be recorded in the breadcrumb data. Errors can be recorded earlier if they were already known.

### -field Unused

Padding buffer reserved for future use.
