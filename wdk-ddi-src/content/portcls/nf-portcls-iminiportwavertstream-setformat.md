---
UID: NF:portcls.IMiniportWaveRTStream.SetFormat
title: IMiniportWaveRTStream::SetFormat (portcls.h)
description: The SetFormat method sets the data format of the wave stream.
tech.root: audio
ms.assetid: b5ab8d1e-c92b-4182-99f5-c36e4e3940af
ms.date: 09/29/2020
keywords: ["IMiniportWaveRTStream::SetFormat"]
ms.keywords: IMiniportWaveRTStream::SetFormat, SetFormat, IMiniportWaveRTStream.SetFormat, IMiniportWaveRTStream::SetFormat, IMiniportWaveRTStream.SetFormat
req.header: portcls.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
f1_keywords:
 - IMiniportWaveRTStream::SetFormat
 - portcls/IMiniportWaveRTStream::SetFormat
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IMiniportWaveRTStream.SetFormat
product:
 - Windows
---

# IMiniportWaveRTStream::SetFormat

## -description

The SetFormat method sets the data format of the wave stream.

## -parameters

### -param DataFormat

[in]
Pointer to a [KSDATAFORMAT](/windows-hardware/drivers/ddi/ks/ns-ks-ksdataformat) structure that describes the requested data format.

## -returns

The following table shows the possible return status codes.

| Return code | Description |
|-------------|-------------|
| STATUS_SUCCESS | The call was successful|
| STATUS_INVALID_PARAMETER| The specified format is either not valid or not supported by the driver, or the format cannot be changed while the stream is running. |

## -remarks

None

## -see-also

[IMiniPortWaveRTStream](nn-portcls-iminiportwavertstream.md)

[KSDATAFORMAT](/windows-hardware/drivers/ddi/ks/ns-ks-ksdataformat)