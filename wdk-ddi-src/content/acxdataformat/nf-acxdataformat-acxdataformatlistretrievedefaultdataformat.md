---
UID: NF:acxdataformat.AcxDataFormatListRetrieveDefaultDataFormat
tech.root: audio
title: AcxDataFormatListRetrieveDefaultDataFormat
ms.date: 12/15/2022
targetos: Windows
description: The AcxDataFormatListRetrieveDefaultDataFormat gets the default ACX data format from the specified ACX data format list.
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
 - AcxDataFormatListRetrieveDefaultDataFormat
f1_keywords:
 - AcxDataFormatListRetrieveDefaultDataFormat
 - acxdataformat/AcxDataFormatListRetrieveDefaultDataFormat
dev_langs:
 - c++
---

## -description

The **AcxDataFormatListRetrieveDefaultDataFormat** gets the default ACX data format from the specified ACX data format list.

## -parameters

### -param AcxDataFormatList [in]

The ACX data format list from which to get the default ACX data format.

### -param AcxDataFormat [out]

Pointer to the default [ACXDATAFORMAT](index.md) object for the *AcxDataFormatList*.

## -returns

The method returns **STATUS_SUCCESS** if the operation succeeds. Otherwise, this method might return an appropriate **[NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values)** error code.

## -remarks

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [ACXDATAFORMAT](index.md)
- [KSDATAFORMAT](../ks/ns-ks-ksdataformat.md)
- [acxdataformat.h header](index.md)
