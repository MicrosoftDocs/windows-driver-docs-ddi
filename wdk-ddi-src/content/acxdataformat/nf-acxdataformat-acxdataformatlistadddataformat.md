---
UID: NF:acxdataformat.AcxDataFormatListAddDataFormat
tech.root: audio
title: AcxDataFormatListAddDataFormat
ms.date: 12/15/2022
targetos: Windows
description: The AcxDataFormatListAddDataFormat function adds an ACXDATAFORMAT object to a data format list.
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
 - AcxDataFormatListAddDataFormat
f1_keywords:
 - AcxDataFormatListAddDataFormat
 - acxdataformat/AcxDataFormatListAddDataFormat
dev_langs:
 - c++
---

## -description

The **AcxDataFormatListAddDataFormat** function adds an [ACXDATAFORMAT](index.md) object to a data format list.

## -parameters

### -param AcxDataFormatList [in]

The data format list to which *AcxDataFormat* is added.

### -param AcxDataFormat [in]

The [ACXDATAFORMAT](index.md) object to add to *AcxDataFormatList*.

## -returns

The method returns **STATUS_SUCCESS** if the operation succeeds. Otherwise, this method might return an appropriate **[NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values)** error code.

## -remarks

If the data format list doesn't have a default data format, this data format becomes the default data format for that list.

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [AcxDataFormatListRemoveDataFormat](nf-acxdataformat-acxdataformatlistremovedataformat.md)
- [KSDATAFORMAT](../ks/ns-ks-ksdataformat.md)
- [acxdataformat.h header](index.md)
