---
UID: NS:gnssdriver.__unnamed_struct_37
title: GNSS_AGNSS_INJECTPOSITION (gnssdriver.h)
description: This structure defines the format for AGNSS position injection.
old-location: gnss\gnss_agnss_injectposition.htm
tech.root: gnss
ms.date: 02/15/2018
keywords: ["GNSS_AGNSS_INJECTPOSITION structure"]
ms.keywords: "*PGNSS_AGNSS_INJECTPOSITION, GNSS_AGNSS_INJECTPOSITION, GNSS_AGNSS_INJECTPOSITION structure [Sensor Devices], PGNSS_AGNSS_INJECTPOSITION, PGNSS_AGNSS_INJECTPOSITION structure pointer [Sensor Devices], gnss.gnss_agnss_injectposition, gnssdriver/GNSS_AGNSS_INJECTPOSITION, gnssdriver/PGNSS_AGNSS_INJECTPOSITION"
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
req.typenames: GNSS_AGNSS_INJECTPOSITION, *PGNSS_AGNSS_INJECTPOSITION
f1_keywords:
 - PGNSS_AGNSS_INJECTPOSITION
 - gnssdriver/PGNSS_AGNSS_INJECTPOSITION
 - GNSS_AGNSS_INJECTPOSITION
 - gnssdriver/GNSS_AGNSS_INJECTPOSITION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - gnssdriver.h
api_name:
 - GNSS_AGNSS_INJECTPOSITION
---

# GNSS_AGNSS_INJECTPOSITION structure


## -description

This structure defines the format for AGNSS position injection.

## -struct-fields

### -field Size

Structure size.

### -field Version

Version number.

### -field Age

Indicates how long the position has been aged in seconds.

### -field BasicData

Position data.

### -field AccuracyData

Position accuracy.

