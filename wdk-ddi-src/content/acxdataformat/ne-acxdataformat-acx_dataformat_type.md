---
UID: NE:acxdataformat._ACX_DATAFORMAT_TYPE
tech.root: audio
title: ACX_DATAFORMAT_TYPE
ms.date: 05/31/2022
targetos: Windows
description: The ACX_DATAFORMAT_TYPE enumeration is used to specify the type of a data format used by an audio class extension (ACX) driver.
prerelease: true
req.construct-type: enumeration
req.ddi-compliance: 
req.header: acxdataformat.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxdataformat.h
api_name:
 - _ACX_DATAFORMAT_TYPE
 - PACX_DATAFORMAT_TYPE
 - ACX_DATAFORMAT_TYPE
f1_keywords:
 - _ACX_DATAFORMAT_TYPE
 - acxdataformat/_ACX_DATAFORMAT_TYPE
 - PACX_DATAFORMAT_TYPE
 - acxdataformat/PACX_DATAFORMAT_TYPE
 - ACX_DATAFORMAT_TYPE
 - acxdataformat/ACX_DATAFORMAT_TYPE
dev_langs:
 - c++
---

## -description

The **ACX_DATAFORMAT_TYPE** enumeration is used to specify the type of a data format used by an audio class extension (ACX) driver.

## -enum-fields

### -field AcxDataFormatKsFormat

The data format is a [KSDATAFORMAT](../ks/ns-ks-ksdataformat.md) type.

### -field AcxDataFormatMaximum

For internal validation, do not use.

## -remarks

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [KSDATAFORMAT](../ks/ns-ks-ksdataformat.md)
- [acxdataformat.h header](index.md)

