---
UID: NS:gnssdriver.__unnamed_struct_48
title: GNSS_CWTESTDATA (gnssdriver.h)
description: This structure defines specific data elements associated with carrier wave test results returned from the driver.
tech.root: gnss
ms.date: 06/16/2022
keywords: ["GNSS_CWTESTDATA structure"]
ms.keywords: "*PGNSS_CWTESTDATA, GNSS_CWTESTDATA, GNSS_CWTESTDATA structure [Sensor Devices], PGNSS_CWTESTDATA, PGNSS_CWTESTDATA structure pointer [Sensor Devices], gnss.gnss_cwtestdata, gnssdriver/GNSS_CWTESTDATA, gnssdriver/PGNSS_CWTESTDATA"
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
req.typenames: GNSS_CWTESTDATA, *PGNSS_CWTESTDATA
f1_keywords:
 - PGNSS_CWTESTDATA
 - gnssdriver/PGNSS_CWTESTDATA
 - GNSS_CWTESTDATA
 - gnssdriver/GNSS_CWTESTDATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - gnssdriver.h
api_name:
 - PGNSS_CWTESTDATA
 - GNSS_CWTESTDATA
---

## -description

This structure defines specific data elements associated with carrier wave test results returned from the driver.

## -struct-fields

### -field Size

Structure size.

### -field Version

Version number.

### -field TestResultStatus

NTSTATUS value indicating whether this fix contains a valid data, or if the GNSS engine or driver encountered any errors in getting the measurements for the carrier wave test.

- Success - carrier wave test successfully started.

- Failed - with error code: test not implemented, carrier wave test already in progress, fix session in progress, or other failure.

### -field SignalToNoiseRatio

Signal to noise ratio in the carrier wave in dB-Hz.

### -field Frequency

Frequency of the carrier wave detected in the measurement band.

This frequency is provided as a difference to GPS frequency (1575.42 MHz) in kHz.

### -field Unused

Padding buffer reserved for future use.
