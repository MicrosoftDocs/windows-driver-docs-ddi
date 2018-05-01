---
UID: NS:gnssdriver.GNSS_AGNSS_INJECTBLOB
title: GNSS_AGNSS_INJECTBLOB
author: windows-driver-content
description: This structure defines the format for AGNSS extended ephemeris injection.
old-location: gnss\gnss_agnss_injectblob.htm
old-project: gnss
ms.assetid: DAC91C40-C9B3-433C-AA64-CE4C021CD8C5
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PGNSS_AGNSS_INJECTBLOB, GNSS_AGNSS_INJECTBLOB, GNSS_AGNSS_INJECTBLOB structure [Sensor Devices], PGNSS_AGNSS_INJECTBLOB, PGNSS_AGNSS_INJECTBLOB structure pointer [Sensor Devices], gnss.gnss_agnss_injectblob, gnssdriver/GNSS_AGNSS_INJECTBLOB, gnssdriver/PGNSS_AGNSS_INJECTBLOB"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	gnssdriver.h
api_name:
-	GNSS_AGNSS_INJECTBLOB
product: Windows
targetos: Windows
req.typenames: GNSS_AGNSS_INJECTBLOB, *PGNSS_AGNSS_INJECTBLOB
---

# GNSS_AGNSS_INJECTBLOB structure


## -description


This structure defines the format for AGNSS extended ephemeris injection.


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

 




#### - BlobData[ANYSIZE_ARRAY]

This field defines the start of the blob data.

The structure only contains the first byte of the blob data. The rest of the blob data is saved right after the structure in the memory. The size of the blob  is indicated by BlobSize.

