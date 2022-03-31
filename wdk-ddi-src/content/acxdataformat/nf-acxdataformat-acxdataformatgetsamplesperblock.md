---
UID: NF:acxdataformat.AcxDataFormatGetSamplesPerBlock
tech.root: audio
title: AcxDataFormatGetSamplesPerBlock
ms.date: 03/24/2022
targetos: Windows
description: The AcxDataFormatGetSamplesPerBlock function gets the number of samples per block for the specified data format.
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
 - AcxDataFormatGetSamplesPerBlock
f1_keywords:
 - AcxDataFormatGetSamplesPerBlock
 - acxdataformat/AcxDataFormatGetSamplesPerBlock
dev_langs:
 - c++
---

## -description

The **AcxDataFormatGetSamplesPerBlock** function gets the number of samples per block for the specified data format.

## -parameters

### -param DataFormat [in]

The data format for which to retrieve the number of samples per block.

## -returns

Returns a ULONG value containing the number of samples per block for the specified *DataFormat*.

## -remarks

Number of samples contained in one compressed block of audio data. This value is used in buffer estimation. This value is used with compressed formats that have a fixed number of samples within each block. This value can be set to zero if a variable number of samples is contained in each block of compressed audio data. In this case, buffer estimation and position information needs to be obtained in other ways.

## -see-also

- [WAVEFORMATEXTENSIBLE structure](/previous-versions/windows/desktop/legacy/dd390971(v=vs.85))

TBD - Please review this topic
