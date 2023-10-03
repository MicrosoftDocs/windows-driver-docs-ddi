---
UID: NF:acxdataformat.AcxDataFormatListCreate
tech.root: audio
title: AcxDataFormatListCreate
ms.date: 12/15/2022
targetos: Windows
description: The AcxDataFormatListCreate function creates a new ACX data format list.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxdataformat.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
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
 - AcxDataFormatListCreate
f1_keywords:
 - AcxDataFormatListCreate
 - acxdataformat/AcxDataFormatListCreate
dev_langs:
 - c++
---

## -description

The **AcxDataFormatListCreate** function creates a new ACX data format list.

## -parameters

### -param Device [in]

The [WDFDEVICE](../wdfdevice/index.md) to which the data format list applies.

### -param Attributes [in]

Pointer to a [WDF_OBJECT_ATTRIBUTES](../wdfobject/ns-wdfobject-_wdf_object_attributes.md) structure used to describe the *Device*.

### -param Config [in]

Pointer to an [ACX_DATAFORMAT_LIST_CONFIG](ns-acxdataformat-acx_dataformat_list_config.md) structure used to configure the *DataFormatList*.

### -param DataFormatList [out]

Pointer to the newly created ACX data format list.

## -returns

The method returns **STATUS_SUCCESS** if the operation succeeds. Otherwise, this method might return an appropriate **[NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values)** error code.

## -remarks

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [WDFDEVICE](../wdfdevice/index.md)
- [WDF_OBJECT_ATTRIBUTES](../wdfobject/ns-wdfobject-_wdf_object_attributes.md)
- [ACX_DATAFORMAT_LIST_CONFIG](ns-acxdataformat-acx_dataformat_list_config.md)
- [acxdataformat.h header](index.md)
