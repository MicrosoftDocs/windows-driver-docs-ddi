---
UID: NS:gnssdriver.GNSS_LKGFIX_PARAM
title: GNSS_LKGFIX_PARAM (gnssdriver.h)
description: This structure is not used currently by the system and is not required to be implemented.
old-location: gnss\gnss_lkgfix_param.htm
tech.root: gnss
ms.date: 02/15/2018
keywords: ["GNSS_LKGFIX_PARAM structure"]
ms.keywords: "*PGNSS_LKGFIX_PARAM, GNSS_LKGFIX_PARAM, GNSS_LKGFIX_PARAM structure [Sensor Devices], PGNSS_LKGFIX_PARAM, PGNSS_LKGFIX_PARAM structure pointer [Sensor Devices], gnss.gnss_lkgfix_param, gnssdriver/GNSS_LKGFIX_PARAM, gnssdriver/PGNSS_LKGFIX_PARAM"
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
req.typenames: GNSS_LKGFIX_PARAM, *PGNSS_LKGFIX_PARAM
f1_keywords:
 - PGNSS_LKGFIX_PARAM
 - gnssdriver/PGNSS_LKGFIX_PARAM
 - GNSS_LKGFIX_PARAM
 - gnssdriver/GNSS_LKGFIX_PARAM
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - gnssdriver.h
api_name:
 - PGNSS_LKGFIX_PARAM
 - GNSS_LKGFIX_PARAM
---

# GNSS_LKGFIX_PARAM structure


## -description

This structure is not used currently by the system and is not required to be implemented.

## -struct-fields

### -field Size

Structure size.

### -field Version

Version number.

## -remarks

No additional parameter is needed for an LKG fix. The GNSS adapter implements any aging heuristics for rejecting an LKG fix received from the GNSS driver based on the difference between the fix time and current time.

