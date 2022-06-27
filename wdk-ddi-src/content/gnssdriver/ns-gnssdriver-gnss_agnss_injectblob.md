---
UID: NS:gnssdriver.__unnamed_struct_42
title: GNSS_AGNSS_INJECTBLOB (gnssdriver.h)
description: The GNSS_AGNSS_INJECTBLOB structure defines the format for AGNSS extended ephemeris injection.
tech.root: gnss
ms.date: 06/20/2022
keywords: ["GNSS_AGNSS_INJECTBLOB structure"]
ms.keywords: "*PGNSS_AGNSS_INJECTBLOB, GNSS_AGNSS_INJECTBLOB, GNSS_AGNSS_INJECTBLOB structure [Sensor Devices], PGNSS_AGNSS_INJECTBLOB, PGNSS_AGNSS_INJECTBLOB structure pointer [Sensor Devices], gnss.gnss_agnss_injectblob, gnssdriver/GNSS_AGNSS_INJECTBLOB, gnssdriver/PGNSS_AGNSS_INJECTBLOB"
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
req.typenames: GNSS_AGNSS_INJECTBLOB, *PGNSS_AGNSS_INJECTBLOB
f1_keywords:
 - PGNSS_AGNSS_INJECTBLOB
 - gnssdriver/PGNSS_AGNSS_INJECTBLOB
 - GNSS_AGNSS_INJECTBLOB
 - gnssdriver/GNSS_AGNSS_INJECTBLOB
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - gnssdriver.h
api_name:
 - PGNSS_AGNSS_INJECTBLOB
 - GNSS_AGNSS_INJECTBLOB
---

## -description

The **GNSS_AGNSS_INJECTBLOB** structure defines the format for AGNSS extended ephemeris injection.

## -struct-fields

### -field Size

Structure size.

### -field Version

Version number.

### -field BlobOui

This field indicates the 3-byte OUI of silicon vendor or device maker.

### -field BlobVersion

Version of the blob from the same vendor.

### -field AgnssFormat

Data format of the blob.

The formats are defined as macros (GNSS_AGNSSFORMAT_*).

### -field BlobSize

Size of the blob data in bytes.

### -field BlobData

This field defines the start of the blob data.

The structure only contains the first byte of the blob data. The rest of the blob data is saved right after the structure in the memory. The size of the blob  is indicated by BlobSize.
