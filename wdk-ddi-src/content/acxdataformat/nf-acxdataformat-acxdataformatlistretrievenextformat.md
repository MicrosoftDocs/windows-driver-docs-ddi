---
UID: NF:acxdataformat.AcxDataFormatListRetrieveNextFormat
tech.root: audio
title: AcxDataFormatListRetrieveNextFormat
ms.date: 12/15/2022
targetos: Windows
description: The AcxDataFormatListRetrieveNextFormat function gets the next ACX data format when iterating an ACX data format list.
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
 - AcxDataFormatListRetrieveNextFormat
f1_keywords:
 - AcxDataFormatListRetrieveNextFormat
 - acxdataformat/AcxDataFormatListRetrieveNextFormat
dev_langs:
 - c++
---

## -description

The **AcxDataFormatListRetrieveNextFormat** function gets the next ACX data format when iterating an ACX data format list.

## -parameters

### -param AcxDataFormatList [in]

The ACX data format list from which to get the next [ACXDATAFORMAT](index.md) object.

### -param Iterator [in, out]

Pointer to the [ACX_DATAFORMAT_LIST_ITERATOR](ns-acxdataformat-acx_dataformat_list_iterator.md) structure used to iterate *AcxDataFormatList*.

### -param Format [out]

Pointer to the next [ACXDATAFORMAT](index.md) object in *AcxDataFormatList*.

## -returns

The method returns **STATUS_SUCCESS** if the operation succeeds. Otherwise, this method might return an appropriate **[NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values)** error code.

## -remarks

After **AcxDataFormatListRetrieveNextFormat** returns, *Iterator* is updated to point to the next data format in the list after *Format*.

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [ACXDATAFORMAT](index.md)
- [ACX_DATAFORMAT_LIST_ITERATOR](ns-acxdataformat-acx_dataformat_list_iterator.md)
- [AcxDataFormatListBeginIteration](nf-acxdataformat-acxdataformatlistbeginiteration.md)
- [AcxDataFormatListEndIteration](nf-acxdataformat-acxdataformatlistenditeration.md)
- [AcxDataFormatListRemoveDataFormat](nf-acxdataformat-acxdataformatlistremovedataformat.md)
- [AcxDataFormatListRetrieveDefaultDataFormat](nf-acxdataformat-acxdataformatlistretrievedefaultdataformat.md)
- [acxdataformat.h header](index.md)
