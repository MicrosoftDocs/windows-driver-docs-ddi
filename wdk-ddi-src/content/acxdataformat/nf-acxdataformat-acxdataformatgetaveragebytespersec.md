---
UID: NF:acxdataformat.AcxDataFormatGetAverageBytesPerSec
tech.root: audio
title: AcxDataFormatGetAverageBytesPerSec
ms.date: 05/31/2022
targetos: Windows
description: The AcxDataFormatGetAverageBytesPerSec function gets the required bytes-per-second transfer rate for the specified data format.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxdataformat.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - acxdataformat.h
api_name:
 - AcxDataFormatGetAverageBytesPerSec
f1_keywords:
 - AcxDataFormatGetAverageBytesPerSec
 - acxdataformat/AcxDataFormatGetAverageBytesPerSec
dev_langs:
 - c++
---

## -description

The **AcxDataFormatGetAverageBytesPerSec** function gets the required bytes-per-second transfer rate for the specified data format.

## -parameters

### -param DataFormat [in]

The data format for which to retrieve the required bytes-per-second transfer rate.

## -returns

Returns a ULONG value containing the required bytes-per-second transfer rate for the specified *DataFormat*.

## -remarks

## -see-also

- [WAVEFORMAT structure](/windows/win32/api/mmreg/ns-mmreg-waveformat)
- [acxdataformat.h header](index.md)

READY2GO

EDITCOMPLETE
