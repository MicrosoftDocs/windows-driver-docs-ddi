---
UID: NS:wdm._TIME_FIELDS
tech.root: kernel
title: TIME_FIELDS
ms.date: 01/25/2022
targetos: Windows
description: The TIME_FIELDS structure describes time information for time conversion routines.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.target-type: 
req.typenames: TIME_FIELDS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _TIME_FIELDS
 - TIME_FIELDS
f1_keywords:
 - _TIME_FIELDS
 - wdm/_TIME_FIELDS
 - TIME_FIELDS
 - wdm/TIME_FIELDS
dev_langs:
 - c++
helpviewer_keywords:
 - _TIME_FIELDS
---

## -description

Describes time information for time conversion routines.

## -struct-fields

### -field Year

Specifies a value from 1601 on.

### -field Month

Specifies a value from 1 to 12.

### -field Day

Specifies a value from 1 to 31.

### -field Hour

Specifies a value from 0 to 23.

### -field Minute

Specifies a value from 0 to 59.

### -field Second

Specifies a value from 0 to 59.

### -field Milliseconds

Specifies a value from 0 to 999.

### -field Weekday

Specifies a value from 0 to 6 (Sunday to Saturday).

## -remarks

## -see-also

[**RtlTimeFieldsToTime**](./nf-wdm-rtltimefieldstotime.md)

[**RtlTimeToTimeFields**](./nf-wdm-rtltimetotimefields.md)
