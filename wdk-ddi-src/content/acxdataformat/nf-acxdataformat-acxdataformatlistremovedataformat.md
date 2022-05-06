---
UID: NF:acxdataformat.AcxDataFormatListRemoveDataFormat
tech.root: audio
title: AcxDataFormatListRemoveDataFormat
ms.date: 05/06/2022
targetos: Windows
description: The AcxDataFormatListRemoveDataFormat function removes the specified ACX data format from an ACX data format list.
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
 - AcxDataFormatListRemoveDataFormat
f1_keywords:
 - AcxDataFormatListRemoveDataFormat
 - acxdataformat/AcxDataFormatListRemoveDataFormat
dev_langs:
 - c++
---

## -description

The **AcxDataFormatListRemoveDataFormat** function removes the specified ACX data format from an ACX data format list.

## -parameters

### -param AcxDataFormatList [in]

The ACX data format list from which to remove *AcxDataFormat*.

### -param AcxDataFormat [in]

The [ACXDATAFORMAT](index.md) object to remove from *AcxDataFormatList*.

## -returns

The method returns **STATUS_SUCCESS** if the operation succeeds. Otherwise, this method might return an appropriate **[NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values)** error code.

## -remarks

## -see-also

- [AcxDataFormatListAddDataFormat](nf-acxdataformat-acxdataformatlistadddataformat.md)
- [KSDATAFORMAT](../ks/ns-ks-ksdataformat.md)
- [acxdataformat.h header](index.md)

TBD - Please review this topic
