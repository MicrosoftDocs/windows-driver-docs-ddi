---
UID: NS:gnssdriver.GNSS_AGNSS_REQUEST_PARAM
title: GNSS_AGNSS_REQUEST_PARAM (gnssdriver.h)
description: This structure defines AGNSS request parameters.
old-location: gnss\gnss_agnss_request_param.htm
tech.root: gnss
ms.date: 02/15/2018
keywords: ["GNSS_AGNSS_REQUEST_PARAM structure"]
ms.keywords: "*PGNSS_AGNSS_REQUEST_PARAM, GNSS_AGNSS_REQUEST_PARAM, GNSS_AGNSS_REQUEST_PARAM structure [Sensor Devices], PGNSS_AGNSS_REQUEST_PARAM, PGNSS_AGNSS_REQUEST_PARAM structure pointer [Sensor Devices], gnss.gnss_agnss_request_param, gnssdriver/GNSS_AGNSS_REQUEST_PARAM, gnssdriver/PGNSS_AGNSS_REQUEST_PARAM"
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
req.typenames: GNSS_AGNSS_REQUEST_PARAM, *PGNSS_AGNSS_REQUEST_PARAM
f1_keywords:
 - PGNSS_AGNSS_REQUEST_PARAM
 - gnssdriver/PGNSS_AGNSS_REQUEST_PARAM
 - GNSS_AGNSS_REQUEST_PARAM
 - gnssdriver/GNSS_AGNSS_REQUEST_PARAM
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - gnssdriver.h
api_name:
 - PGNSS_AGNSS_REQUEST_PARAM
 - GNSS_AGNSS_REQUEST_PARAM
---

# GNSS_AGNSS_REQUEST_PARAM structure


## -description

This structure defines AGNSS request parameters.

## -struct-fields

### -field Size

Structure size.

### -field Version

Version number.

### -field RequestType

Specifies the type of the request (for example, time injection, blob injection).

### -field BlobFormat

If the RequestType is GNSS_AGNSS_BlobInjection, this contains the required  blob format.

