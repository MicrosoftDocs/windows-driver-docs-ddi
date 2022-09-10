---
UID: NS:gnssdriver.__unnamed_struct_49
title: GNSS_SELFTESTCONFIG (gnssdriver.h)
description: The GNSS_SELFTESTCONFIG structure defines the specific data elements associated with a carrier wave test results returned from the driver.
tech.root: gnss
ms.date: 06/16/2022
keywords: ["GNSS_SELFTESTCONFIG structure"]
ms.keywords: "*PGNSS_SELFTESTCONFIG, GNSS_SELFTESTCONFIG, GNSS_SELFTESTCONFIG structure [Sensor Devices], PGNSS_SELFTESTCONFIG, PGNSS_SELFTESTCONFIG structure pointer [Sensor Devices], gnss.gnss_selftestconfig, gnssdriver/GNSS_SELFTESTCONFIG, gnssdriver/PGNSS_SELFTESTCONFIG"
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
req.typenames: GNSS_SELFTESTCONFIG, *PGNSS_SELFTESTCONFIG
f1_keywords:
 - PGNSS_SELFTESTCONFIG
 - gnssdriver/PGNSS_SELFTESTCONFIG
 - GNSS_SELFTESTCONFIG
 - gnssdriver/GNSS_SELFTESTCONFIG
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - gnssdriver.h
api_name:
 - PGNSS_SELFTESTCONFIG
 - GNSS_SELFTESTCONFIG
---

## -description

This structure defines the specific data elements associated with a carrier wave test results returned from the driver.

## -struct-fields

### -field Size

Structure size.

### -field Version

Version number.

### -field TestType

The type of self-test requested.

### -field Unused

Padding buffer reserved for future use.

### -field InBufLen

The length of the buffer for passing in any additional information about the self-test.

### -field InBuffer

The buffer that will contain the additional information about the self-test.
