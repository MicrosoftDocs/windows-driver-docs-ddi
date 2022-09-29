---
UID: NF:acxpin.AcxPinGetRawDataFormatList
tech.root: audio
title: AcxPinGetRawDataFormatList
ms.date: 04/11/2022
targetos: Windows
description: The AcxPinGetRawDataFormatList function returns the raw mode data format list for the specified pin.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxpin.h
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
 - acxpin.h
api_name:
 - AcxPinGetRawDataFormatList
f1_keywords:
 - AcxPinGetRawDataFormatList
 - acxpin/AcxPinGetRawDataFormatList
dev_langs:
 - c++
---

## -description

The **AcxPinGetRawDataFormatList** function returns the raw mode data format list for the specified pin.

## -parameters

### -param AcxPin

The pin for which to get the data format list.

## -returns

Returns the [ACXDATAFORMATLIST](../acxdataformat/index.md) for the pin specified by *AcxPin*.

## -remarks

This DDI returns NULL if the specified pin doesn't have a raw mode data format list.

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [ACXDATAFORMATLIST](../acxdataformat/index.md)
- [acxpin.h header](index.md)


