---
UID: NF:acxdataformat.AcxDataFormatGetWaveFormatExtensible
tech.root: audio
title: AcxDataFormatGetWaveFormatExtensible
ms.date: 12/15/2022
targetos: Windows
description: The AcxDataFormatGetWaveFormatExtensible function gets the WAVEFORMATEXTENSIBLE structure associated with the specified data format.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxdataformat.h
req.idl: 
req.include-header: 
req.irql: DISPATCH_LEVEL
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
 - AcxDataFormatGetWaveFormatExtensible
f1_keywords:
 - AcxDataFormatGetWaveFormatExtensible
 - acxdataformat/AcxDataFormatGetWaveFormatExtensible
dev_langs:
 - c++
---

## -description

The **AcxDataFormatGetWaveFormatExtensible** function gets the [WAVEFORMATEXTENSIBLE](../ksmedia/ns-ksmedia-waveformatextensible.md) structure associated with the specified data format.

## -parameters

### -param DataFormat [in]

The data format for which to retrieve the [WAVEFORMATEXTENSIBLE](../ksmedia/ns-ksmedia-waveformatextensible.md) structure.

## -returns

Returns a pointer to the [WAVEFORMATEXTENSIBLE](../ksmedia/ns-ksmedia-waveformatextensible.md) structure associated with the specified *DataFormat*.

## -remarks

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [WAVEFORMATEXTENSIBLE](../ksmedia/ns-ksmedia-waveformatextensible.md)
- [acxdataformat.h header](index.md)
