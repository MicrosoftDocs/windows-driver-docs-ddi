---
UID: NF:acxdataformat.AcxDataFormatGetSpecifier
tech.root: audio
title: AcxDataFormatGetSpecifier
ms.date: 05/31/2022
targetos: Windows
description: The AcxDataFormatGetSpecifier function gets the specifier for the specified data format.
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
 - AcxDataFormatGetSpecifier
f1_keywords:
 - AcxDataFormatGetSpecifier
 - acxdataformat/AcxDataFormatGetSpecifier
dev_langs:
 - c++
---

## -description

The **AcxDataFormatGetSpecifier** function gets the audio format specifier for the specified data format.

## -parameters

### -param DataFormat [in]

The data format for which to retrieve the audio format specifier.

## -returns

Returns a GUID value representing the audio format specifier for the *DataFormat*.

## -remarks

Specifies additional data format type information for a specific setting of MajorFormat and SubFormat. The significance of this field is determined by the major format and subformat. For example, the specifier can represent a particular encoding of a subformat, or it can be used to specify what type of data structure follows [KSDATAFORMAT](../ks/ns-ks-ksdataformat.md) in memory.

## -see-also

- [KSDATAFORMAT](../ks/ns-ks-ksdataformat.md)
- [Audio Data Formats](/windows-hardware/drivers/audio/audio-data-formats)
- [acxdataformat.h header](index.md)

