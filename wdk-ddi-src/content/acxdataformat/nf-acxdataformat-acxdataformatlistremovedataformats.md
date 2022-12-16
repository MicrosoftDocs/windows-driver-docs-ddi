---
UID: NF:acxdataformat.AcxDataFormatListRemoveDataFormats
tech.root: audio
title: AcxDataFormatListRemoveDataFormats
ms.date: 12/15/2022
targetos: Windows
description: The AcxDataFormatListRemoveDataFormats function removes all data formats from the specified ACX data format list.
prerelease: false
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
 - AcxDataFormatListRemoveDataFormats
f1_keywords:
 - AcxDataFormatListRemoveDataFormats
 - acxdataformat/AcxDataFormatListRemoveDataFormats
dev_langs:
 - c++
helpviewer_keywords:
 - AcxDataFormatListRemoveDataFormats
---

## -description

The **AcxDataFormatListRemoveDataFormats** function removes all data formats from the specified ACX data format list.

## -parameters

### -param AcxDataFormatList [in]

The data format list from which to delete all data formats.

## -returns

The method returns **STATUS_SUCCESS** if the operation succeeds. Otherwise, this method might return an appropriate **[NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values)** error code.

## -remarks

### ACX requirements

**Minimum ACX version:** 1.1

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [AcxDataFormatListRemoveDataFormat](./nf-acxdataformat-acxdataformatlistremovedataformat.md)
- [AcxDataFormatListAddDataFormat](nf-acxdataformat-acxdataformatlistadddataformat.md)
- [KSDATAFORMAT](../ks/ns-ks-ksdataformat.md)
- [acxdataformat.h header](index.md)
