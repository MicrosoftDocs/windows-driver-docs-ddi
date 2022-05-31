---
UID: NF:acxdataformat.AcxDataFormatCreate
tech.root: audio
title: AcxDataFormatCreate
ms.date: 05/31/2022
targetos: Windows
description: The AcxDataFormatCreate function is used to create a data format for use by an audio class extension (ACX) driver.
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
 - AcxDataFormatCreate
f1_keywords:
 - AcxDataFormatCreate
 - acxdataformat/AcxDataFormatCreate
dev_langs:
 - c++
---

## -description

The **AcxDataFormatCreate** function is used to create a data format for use by an audio class extension (ACX) driver.

## -parameters

### -param Device [in]

A WDFDEVICE object (described in [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) that will be associated with the data format.

### -param Attributes [in]

A pointer to the [WDF_OBJECT_ATTRIBUTES](../wdfobject/ns-wdfobject-_wdf_object_attributes.md) structure to use when creating the data format

### -param Config [in]

A pointer to the [ACX_DATAFORMAT_CONFIG](ns-acxdataformat-acx_dataformat_config.md) structure to use when creating the data format.

### -param DataFormat [out]

A pointer to the newly created data format.

## -returns

The method returns **STATUS_SUCCESS** if the operation succeeds. Otherwise, this method might return an appropriate **[NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values)** error code.

## -remarks

## -see-also

- [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)
- [WDF_OBJECT_ATTRIBUTES](../wdfobject/ns-wdfobject-_wdf_object_attributes.md)
- [ACX_DATAFORMAT_CONFIG](ns-acxdataformat-acx_dataformat_config.md)
- [acxdataformat.h header](index.md)

READY2GO

EDITCOMPLETE
