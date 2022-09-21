---
UID: NF:acxdataformat.AcxDataFormatListAssignDefaultDataFormat
tech.root: audio
title: AcxDataFormatListAssignDefaultDataFormat
ms.date: 05/31/2022
targetos: Windows
description: The AcxDataFormatListAssignDefaultDataFormat function adds an ACXDATAFORMAT object to the specified data format list and sets the ACXDATAFORMAT object as the default.
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
 - AcxDataFormatListAssignDefaultDataFormat
f1_keywords:
 - AcxDataFormatListAssignDefaultDataFormat
 - acxdataformat/AcxDataFormatListAssignDefaultDataFormat
dev_langs:
 - c++
---

## -description

The **AcxDataFormatListAssignDefaultDataFormat** function adds an [ACXDATAFORMAT](index.md) object to the specified data format list and sets the **ACXDATAFORMAT** object as the default.

## -parameters

### -param AcxDataFormatList [in]

The data format list to which the the [ACXDATAFORMAT](index.md) object is added and assigned as the default.

### -param AcxDataFormat [in]

The [ACXDATAFORMAT](index.md) object to add and assign as the default in the *AcxDataFormatList*.

## -returns

The method returns **STATUS_SUCCESS** if the operation succeeds. Otherwise, this method might return an appropriate **[NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values)** error code.

## -remarks

### ACX requirements

| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum ACX version** | 1.0 |

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [ACXDATAFORMAT](index.md) object
- [KSDATAFORMAT](../ks/ns-ks-ksdataformat.md)
- [AcxDataFormatListRetrieveDefaultDataFormat](nf-acxdataformat-acxdataformatlistretrievedefaultdataformat.md)
- [acxdataformat.h header](index.md)

