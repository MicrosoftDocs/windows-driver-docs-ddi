---
UID: NS:gnssdriver.__unnamed_struct_46
title: GNSS_V2UPL_CONFIG (gnssdriver.h)
description: This structure contains V2UPL configuration information.
tech.root: gnss
ms.date: 06/16/2022
keywords: ["GNSS_V2UPL_CONFIG structure"]
ms.keywords: "*PGNSS_V2UPL_CONFIG, GNSS_V2UPL_CONFIG, GNSS_V2UPL_CONFIG structure [Sensor Devices], PGNSS_V2UPL_CONFIG, PGNSS_V2UPL_CONFIG structure pointer [Sensor Devices], gnss.gnss_v2upl_config, gnssdriver/GNSS_V2UPL_CONFIG, gnssdriver/PGNSS_V2UPL_CONFIG"
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
req.typenames: GNSS_V2UPL_CONFIG, *PGNSS_V2UPL_CONFIG
f1_keywords:
 - PGNSS_V2UPL_CONFIG
 - gnssdriver/PGNSS_V2UPL_CONFIG
 - GNSS_V2UPL_CONFIG
 - gnssdriver/GNSS_V2UPL_CONFIG
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - gnssdriver.h
api_name:
 - PGNSS_V2UPL_CONFIG
 - GNSS_V2UPL_CONFIG
---

## -description

This structure contains V2UPL configuration information.

## -struct-fields

### -field Size

Structure size.

### -field Version

Version number.

### -field MPC

MPC address and port number.

### -field PDE

PDE address and port number.

### -field ApplicationTypeIndicator_MR

Application type indicator for any mobile originated location request to the MPC. It shall be set to the value for Microsoft resident applications based on intelligent platform.

### -field Unused

Padding buffer reserved for future use.
