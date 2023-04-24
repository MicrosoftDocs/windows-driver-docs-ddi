---
UID: NS:gnssdriver.GNSS_SUPL_HSLP_CONFIG
title: GNSS_SUPL_HSLP_CONFIG (gnssdriver.h)
description: The GNSS_SUPL_HSLP_CONFIG structure contains SUPL H-SLP configuration information.
tech.root: gnss
ms.date: 06/20/2022
keywords: ["GNSS_SUPL_HSLP_CONFIG structure"]
ms.keywords: "*PGNSS_SUPL_HSLP_CONFIG, GNSS_SUPL_HSLP_CONFIG, GNSS_SUPL_HSLP_CONFIG structure [Sensor Devices], PGNSS_SUPL_HSLP_CONFIG, PGNSS_SUPL_HSLP_CONFIG structure pointer [Sensor Devices], gnss.gnss_supl_hslp_config, gnssdriver/GNSS_SUPL_HSLP_CONFIG, gnssdriver/PGNSS_SUPL_HSLP_CONFIG"
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
req.typenames: GNSS_SUPL_HSLP_CONFIG, *PGNSS_SUPL_HSLP_CONFIG
f1_keywords:
 - PGNSS_SUPL_HSLP_CONFIG
 - gnssdriver/PGNSS_SUPL_HSLP_CONFIG
 - GNSS_SUPL_HSLP_CONFIG
 - gnssdriver/GNSS_SUPL_HSLP_CONFIG
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - gnssdriver.h
api_name:
 - PGNSS_SUPL_HSLP_CONFIG
 - GNSS_SUPL_HSLP_CONFIG
---

## -description

The **GNSS_SUPL_HSLP_CONFIG** structure contains SUPL H-SLP configuration information.

## -struct-fields

### -field Size

Structure size.

### -field Version

Version number.

### -field SuplHslp

This is the SUPL server address with TCP port. The server address will be a FQDN as indicated in the OMA SUPL specs.

### -field SuplHslpFromImsi

This is the SUPL server address as derived from IMSI.

### -field Reserved

Reserved for future use.

### -field Unused

Padding buffer reserved for future use.

