---
UID: NF:printerextension.IPrintSchemaParameterDefinition.get_RangeMin
title: IPrintSchemaParameterDefinition::get_RangeMin (printerextension.h)
description: The RangeMin property gets the minimum value of the allowed data range.
old-location: print\_iprintschemaparameterdefinition_rangemin.htm
tech.root: print
ms.assetid: ED8A29D9-84CE-4FB5-BCEE-C31DA9AB3D00
ms.date: 10/01/2020
keywords: ["IPrintSchemaParameterDefinition::get_RangeMin"]
ms.keywords: IPrintSchemaParameterDefinition interface [Print Devices],RangeMin property, IPrintSchemaParameterDefinition.RangeMin, IPrintSchemaParameterDefinition.get_RangeMin, IPrintSchemaParameterDefinition::RangeMin, IPrintSchemaParameterDefinition::get_RangeMin, RangeMin property [Print Devices], RangeMin property [Print Devices],IPrintSchemaParameterDefinition interface, get_RangeMin, print._iprintschemaparameterdefinition_rangemin, printerextension/IPrintSchemaParameterDefinition::RangeMin, printerextension/IPrintSchemaParameterDefinition::get_RangeMin
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
 - IPrintSchemaParameterDefinition::get_RangeMin
 - printerextension/IPrintSchemaParameterDefinition::get_RangeMin
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrintSchemaParameterDefinition.RangeMin
 - IPrintSchemaParameterDefinition.get_RangeMin
---

# IPrintSchemaParameterDefinition::get_RangeMin

## -description

The **RangeMin** property gets the minimum value of the allowed data range.

This property is read-only.

## -parameters

## -remarks

For the **PrintSchemaParameterDataType_Integer** data type, the value returned by  **RangeMin** maps to the **psf:MinValue** property value of the Print Schema parameter definition. This minimum value shows the minimum integer value that the driver supports.

For the **PrintSchemaParameterDataType_NumericString** and **PrintSchemaParameterDataType_String**  data types, this maps to the **psf:MinLength** property value of the Print Schema parameter definition. This minimum value shows the minimum length of string that the driver supports.

## -see-also

[IPrintSchemaParameterDefinition](nn-printerextension-iprintschemaparameterdefinition.md)
