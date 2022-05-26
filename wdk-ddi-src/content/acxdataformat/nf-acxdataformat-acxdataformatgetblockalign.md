---
UID: NF:acxdataformat.AcxDataFormatGetBlockAlign
tech.root: audio
title: AcxDataFormatGetBlockAlign
ms.date: 05/06/2022
targetos: Windows
description: The AcxDataFormatGetBlockAlign function gets the block alignment of the specified data format.
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
 - AcxDataFormatGetBlockAlign
f1_keywords:
 - AcxDataFormatGetBlockAlign
 - acxdataformat/AcxDataFormatGetBlockAlign
dev_langs:
 - c++
---

## -description

The **AcxDataFormatGetBlockAlign** function gets the block alignment of the specified data format.

## -parameters

### -param DataFormat [in]

The data format for which to retrieve the block alignment.

## -returns

Returns a ULONG value containing the block alignment, in bytes, for the specified data format. The block alignment is the minimum atomic unit of data for the *DataFormat* type.

## -remarks

## -see-also

- [WAVEFORMAT structure](/windows/win32/api/mmreg/ns-mmreg-waveformat)
- [acxdataformat.h header](index.md)

READY2GO
