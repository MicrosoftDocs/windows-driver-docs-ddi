---
UID: NS:gnssdriver.GNSS_AGNSS_INJECT
title: GNSS_AGNSS_INJECT (gnssdriver.h)
description: The GNSS_AGNSS_INJECT structure defines the parameters for AGNSS injection.
tech.root: gnss
ms.date: 06/20/2022
keywords: ["GNSS_AGNSS_INJECT structure"]
ms.keywords: "*PGNSS_AGNSS_INJECT, GNSS_AGNSS_INJECT, GNSS_AGNSS_INJECT structure [Sensor Devices], PGNSS_AGNSS_INJECT, PGNSS_AGNSS_INJECT structure pointer [Sensor Devices], gnss.gnss_agnss_inject, gnssdriver/GNSS_AGNSS_INJECT, gnssdriver/PGNSS_AGNSS_INJECT"
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
req.typenames: GNSS_AGNSS_INJECT, *PGNSS_AGNSS_INJECT
f1_keywords:
 - PGNSS_AGNSS_INJECT
 - gnssdriver/PGNSS_AGNSS_INJECT
 - GNSS_AGNSS_INJECT
 - gnssdriver/GNSS_AGNSS_INJECT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - gnssdriver.h
api_name:
 - PGNSS_AGNSS_INJECT
 - GNSS_AGNSS_INJECT
---

## -description

The **GNSS_AGNSS_INJECT** structure defines the parameters for AGNSS injection.

## -struct-fields

### -field Size

Structure size.

### -field Version

Version number.

### -field InjectionType

Indicates the specific type of AGNSS injection.

Depending on the type, the driver must access the specific data element of the structure. For example, if the type is GNSS_AGNSS_PositionInjection, use the Position element.

### -field InjectionStatus

Indicates whether any error was encountered in gathering the needed injection data.

The driver must ignore the injection if this field does not indicate success.

### -field InjectionDataSize

Size of the injection data.

### -field Unused

Padding buffer reserved for future use.

### -field Time

[GNSS_AGNSS_INJECTTIME](./ns-gnssdriver-gnss_agnss_injecttime.md) contains the format for AGNSS time injection.

### -field Position

[GNSS_AGNSS_INJECTPOSITION](./ns-gnssdriver-gnss_agnss_injectposition.md) contains  the format for AGNSS position injection.

### -field BlobData

[GNSS_AGNSS_INJECTBLOB](./ns-gnssdriver-gnss_agnss_injectblob.md)  contains the format for AGNSS extended ephemeris injection.

