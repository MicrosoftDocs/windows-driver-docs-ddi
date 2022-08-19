---
UID: NF:printerextension.IPrintSchemaParameterDefinition.get_UserInputRequired
title: IPrintSchemaParameterDefinition::get_UserInputRequired (printerextension.h)
description: The UserInputRequired property gets the Boolean value that indicates whether or not a user input value is required for the Print Schema parameter.
tech.root: print
ms.date: 08/03/2022
keywords: ["IPrintSchemaParameterDefinition::get_UserInputRequired"]
ms.keywords: IPrintSchemaParameterDefinition interface [Print Devices],UserInputRequired property, IPrintSchemaParameterDefinition.UserInputRequired, IPrintSchemaParameterDefinition.get_UserInputRequired, IPrintSchemaParameterDefinition::UserInputRequired, IPrintSchemaParameterDefinition::get_UserInputRequired, UserInputRequired property [Print Devices], UserInputRequired property [Print Devices],IPrintSchemaParameterDefinition interface, get_UserInputRequired, print._iprintschemaparameterdefinition_userinputrequired, printerextension/IPrintSchemaParameterDefinition::UserInputRequired, printerextension/IPrintSchemaParameterDefinition::get_UserInputRequired
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
 - IPrintSchemaParameterDefinition::get_UserInputRequired
 - printerextension/IPrintSchemaParameterDefinition::get_UserInputRequired
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrintSchemaParameterDefinition::get_UserInputRequired
---

## -description

The **UserInputRequired** property gets the Boolean value that indicates whether or not a user input value is required for the Print Schema parameter.

This property is read-only.

## -parameters

### -param pbIsRequired

Defines the **BOOL** parameter *pbIsRequired*.

## -returns

Returns an **HRESULT** value. If the property call was not successful, it returns the appropriate **HRESULT** error code.

## -remarks

The print dialog can use **UserInputRequired** to determine whether or not it should force the user to enter a valid value for the parameter, before it allows printing to proceed.

## -see-also

[IPrintSchemaParameterDefinition](./nn-printerextension-iprintschemaparameterdefinition.md)