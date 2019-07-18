---
UID: NS:gnssdriver.__unnamed_struct_39
title: GNSS_SUPL_HSLP_CONFIG (gnssdriver.h)
description: This structure contains SUPL H-SLP configuration information.
old-location: gnss\gnss_supl_hslp_config.htm
tech.root: gnss
ms.assetid: 08CCC4A8-2D85-436D-B18E-77C91A24F59C
ms.date: 02/15/2018
ms.keywords: "*PGNSS_SUPL_HSLP_CONFIG, GNSS_SUPL_HSLP_CONFIG, GNSS_SUPL_HSLP_CONFIG structure [Sensor Devices], PGNSS_SUPL_HSLP_CONFIG, PGNSS_SUPL_HSLP_CONFIG structure pointer [Sensor Devices], gnss.gnss_supl_hslp_config, gnssdriver/GNSS_SUPL_HSLP_CONFIG, gnssdriver/PGNSS_SUPL_HSLP_CONFIG"
ms.topic: struct
f1_keywords:
 - "gnssdriver/GNSS_SUPL_HSLP_CONFIG"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- gnssdriver.h
api_name:
- GNSS_SUPL_HSLP_CONFIG
product:
- Windows
targetos: Windows
req.typenames: GNSS_SUPL_HSLP_CONFIG, *PGNSS_SUPL_HSLP_CONFIG
---

# GNSS_SUPL_HSLP_CONFIG structure


## -description


This structure contains SUPL H-SLP configuration information.


## -struct-fields




### -field Size

Structure size.


### -field Version

Version number.


### -field SuplHslp

 


### -field SuplHslpFromImsi

 


### -field Reserved

Reserved for future use.


### -field Unused

 




#### - SuplHslpFromImsi[MAX_SERVER_URL_NAME]

This is the SUPL server address as derived from IMSI.


#### - SuplHslp[MAX_SERVER_URL_NAME]

This is the SUPL server address with TCP port. The server address will be a FQDN as indicated in the OMA SUPL specs.


#### - Unused[512]

Padding buffer.

