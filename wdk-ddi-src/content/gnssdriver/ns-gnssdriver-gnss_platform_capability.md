---
UID: NS:gnssdriver.__unnamed_struct_3
title: GNSS_PLATFORM_CAPABILITY (gnssdriver.h)
description: The GNSS_PLATFORM_CAPABILITY structure is used to communicate the platform/HLOS capabilities to the underlying GNSS driver.
tech.root: gnss
ms.date: 06/17/2022
keywords: ["GNSS_PLATFORM_CAPABILITY structure"]
ms.keywords: "*PGNSS_PLATFORM_CAPABILITY, GNSS_PLATFORM_CAPABILITY, GNSS_PLATFORM_CAPABILITY structure [Sensor Devices], PGNSS_PLATFORM_CAPABILITY, PGNSS_PLATFORM_CAPABILITY structure pointer [Sensor Devices], gnss.gnss_platform_capability, gnssdriver/GNSS_PLATFORM_CAPABILITY, gnssdriver/PGNSS_PLATFORM_CAPABILITY"
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
req.typenames: GNSS_PLATFORM_CAPABILITY, *PGNSS_PLATFORM_CAPABILITY
f1_keywords:
 - PGNSS_PLATFORM_CAPABILITY
 - gnssdriver/PGNSS_PLATFORM_CAPABILITY
 - GNSS_PLATFORM_CAPABILITY
 - gnssdriver/GNSS_PLATFORM_CAPABILITY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - gnssdriver.h
api_name:
 - PGNSS_PLATFORM_CAPABILITY
 - GNSS_PLATFORM_CAPABILITY
---

## -description

The **GNSS_PLATFORM_CAPABILITY** structure is used to communicate the platform/HLOS capabilities to the underlying GNSS driver.

## -struct-fields

### -field Size

Structure size.

### -field Version

Version number.

### -field SupportAgnssInjection

Indicates that the platform supports AGNSS injection via the location platform.

### -field AgnssFormatSupported

Specifies a bitmask containing the different AGNSS formats (GNSS_AGNSSFORMAT_*) that the GNSS driver or device supports.

### -field Unused

Padding buffer reserved for future use.

## -remarks

 This is a list of individual capability support of the GNSS adapter. The platform capability is represented in the same way as the device capabilities are represented.
