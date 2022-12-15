---
UID: NF:acxdataformat.AcxDataFormatGetChannelsCount
tech.root: audio
title: AcxDataFormatGetChannelsCount
ms.date: 12/15/2022
targetos: Windows
description: The AcxDataFormatGetChannelsCount function gets the number of audio channels in the specified data format.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxdataformat.h
req.idl: 
req.include-header: 
req.irql: <= DISPATCH_LEVEL
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
 - AcxDataFormatGetChannelsCount
f1_keywords:
 - AcxDataFormatGetChannelsCount
 - acxdataformat/AcxDataFormatGetChannelsCount
dev_langs:
 - c++
---

## -description

The **AcxDataFormatGetChannelsCount** function gets the number of audio channels in the specified data format.

## -parameters

### -param DataFormat [in]

The data format for which to retrieve the count of channels.

## -returns

Returns a USHORT value containing the number of channels specified in the *DataFormat*.

## -remarks

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [WAVEFORMAT structure](/windows/win32/api/mmreg/ns-mmreg-waveformat)
- [acxdataformat.h header](index.md)

