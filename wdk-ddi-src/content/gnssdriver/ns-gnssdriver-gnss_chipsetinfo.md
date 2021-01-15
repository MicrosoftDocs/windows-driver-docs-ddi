---
UID: NS:gnssdriver.__unnamed_struct_47
title: GNSS_CHIPSETINFO (gnssdriver.h)
description: This structure defines the specific data elements associated with the GNSS hardware.
old-location: gnss\gnss_chipsetinfo.htm
tech.root: gnss
ms.date: 05/11/2020
keywords: ["GNSS_CHIPSETINFO structure"]
ms.keywords: "*PGNSS_CHIPSETINFO, GNSS_CHIPSETINFO, GNSS_CHIPSETINFO structure [Sensor Devices], PGNSS_CHIPSETINFO, PGNSS_CHIPSETINFO structure pointer [Sensor Devices], gnss.gnss_chipsetinfo, gnssdriver/GNSS_CHIPSETINFO, gnssdriver/PGNSS_CHIPSETINFO"
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
req.typenames: GNSS_CHIPSETINFO, *PGNSS_CHIPSETINFO
f1_keywords:
 - PGNSS_CHIPSETINFO
 - gnssdriver/PGNSS_CHIPSETINFO
 - GNSS_CHIPSETINFO
 - gnssdriver/GNSS_CHIPSETINFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - gnssdriver.h
api_name:
 - PGNSS_CHIPSETINFO
 - GNSS_CHIPSETINFO
---

# GNSS_CHIPSETINFO structure


## -description

This structure defines the specific data elements associated with the GNSS hardware.

## -struct-fields

### -field Size

 The structure size.

### -field Version

The version number.

### -field ManufacturerID

The manufacturer ID value.

### -field HardwareID

The hardware ID value.

### -field FirmwareVersion

The firmware version value.

### -field Unused

Reserved for future use.

#### - FirmwareVersion[20]

Version of the firmware for the GNSS chipset. This would be a string, typically of the format NNNN.NNNN.NNNN.NNNN.

#### - HardwareID[25]

String containing an identifier for the specific GNSS chipset or combo chipset.

#### - ManufacturerID[25]

String containing an identifier for the manufacturer.

#### - Unused[512]

Padding buffer reserved for future use.

