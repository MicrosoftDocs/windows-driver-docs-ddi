---
UID: NF:printerextension.IPrintSchemaParameterDefinition.get_DataType
title: IPrintSchemaParameterDefinition::get_DataType (printerextension.h)
description: The DataType property gets the PrintSchemaParameterDataType enumerated value that indicates the expected data type for the Print Schema parameter.
tech.root: print
ms.date: 08/03/2022
keywords: ["IPrintSchemaParameterDefinition::get_DataType"]
ms.keywords: DataType property [Print Devices], DataType property [Print Devices],IPrintSchemaParameterDefinition interface, IPrintSchemaParameterDefinition interface [Print Devices],DataType property, IPrintSchemaParameterDefinition.DataType, IPrintSchemaParameterDefinition.get_DataType, IPrintSchemaParameterDefinition::DataType, IPrintSchemaParameterDefinition::get_DataType, get_DataType, print._iprintschemaparameterdefinition_datatype, printerextension/IPrintSchemaParameterDefinition::DataType, printerextension/IPrintSchemaParameterDefinition::get_DataType
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IPrintSchemaParameterDefinition::get_DataType
 - printerextension/IPrintSchemaParameterDefinition::get_DataType
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrintSchemaParameterDefinition::get_DataType
---

## -description

The **DataType** property gets the [PrintSchemaParameterDataType](/windows-hardware/drivers/ddi/printerextension/ne-printerextension-tagprintschemaparameterdatatype) enumerated value that indicates the expected data type for the Print Schema parameter.

This property is read-only.

## -parameters

### -param pDataType

Defines the **PrintSchemaParameterDataType** parameter *pDataType*.

## -returns

Returns an **HRESULT** value. If the property call was not successful, it returns the appropriate **HRESULT** error code.

## -see-also

[IPrintSchemaParameterDefinition](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemaparameterdefinition)

[PrintSchemaParameterDataType](/windows-hardware/drivers/ddi/printerextension/ne-printerextension-tagprintschemaparameterdatatype)
