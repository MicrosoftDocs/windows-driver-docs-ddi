---
UID: NS:gnssdriver.__unnamed_struct_6
title: GNSS_DISTANCETRACKING_PARAM (gnssdriver.h)
description: This structure defines the parameters for a distance-based tracking fix session.
old-location: gnss\gnss_distancetracking_param.htm
tech.root: gnss
ms.date: 02/15/2018
keywords: ["GNSS_DISTANCETRACKING_PARAM structure"]
ms.keywords: "*PGNSS_DISTANCETRACKING_PARAM, GNSS_DISTANCETRACKING_PARAM, GNSS_DISTANCETRACKING_PARAM structure [Sensor Devices], PGNSS_DISTANCETRACKING_PARAM, PGNSS_DISTANCETRACKING_PARAM structure pointer [Sensor Devices], gnss.gnss_distancetracking_param, gnssdriver/GNSS_DISTANCETRACKING_PARAM, gnssdriver/PGNSS_DISTANCETRACKING_PARAM"
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
targetos: Windows
req.typenames: GNSS_DISTANCETRACKING_PARAM, *PGNSS_DISTANCETRACKING_PARAM
f1_keywords:
 - PGNSS_DISTANCETRACKING_PARAM
 - gnssdriver/PGNSS_DISTANCETRACKING_PARAM
 - GNSS_DISTANCETRACKING_PARAM
 - gnssdriver/GNSS_DISTANCETRACKING_PARAM
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - gnssdriver.h
api_name:
 - GNSS_DISTANCETRACKING_PARAM
---

# GNSS_DISTANCETRACKING_PARAM structure


## -description

This structure defines the parameters for a distance-based tracking fix session.

## -struct-fields

### -field Size

Structure size.

### -field Version

Version number.

### -field MovementThreshold

If the device moves beyond this threshold, a fix will be generated/recorded. A value of zero indicates that a fix should be reported whenever the device moves. This value is specified in meters.

