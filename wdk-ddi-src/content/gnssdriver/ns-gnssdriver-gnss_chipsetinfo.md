---
UID: NS:gnssdriver.__unnamed_struct_51
title: GNSS_CHIPSETINFO (gnssdriver.h)
description: This structure defines the specific data elements associated with the GNSS hardware.
tech.root: gnss
ms.date: 06/16/2022
keywords: ["GNSS_CHIPSETINFO structure"]
ms.keywords: "*PGNSS_CHIPSETINFO, GNSS_CHIPSETINFO, GNSS_CHIPSETINFO structure [Sensor Devices], PGNSS_CHIPSETINFO, PGNSS_CHIPSETINFO structure pointer [Sensor Devices], gnss.gnss_chipsetinfo, gnssdriver/GNSS_CHIPSETINFO, gnssdriver/PGNSS_CHIPSETINFO"
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

## -description

This structure defines the specific data elements associated with the GNSS hardware.

## -struct-fields

### -field Size

 The structure size.

### -field Version

The version number.

### -field ManufacturerID

String containing an identifier for the manufacturer.

### -field HardwareID

String containing an identifier for the specific GNSS chipset or combo chipset.

### -field FirmwareVersion

Version of the firmware for the GNSS chipset. This would be a string, typically of the format NNNN.NNNN.NNNN.NNNN.

### -field Unused

Padding buffer reserved for future use.
