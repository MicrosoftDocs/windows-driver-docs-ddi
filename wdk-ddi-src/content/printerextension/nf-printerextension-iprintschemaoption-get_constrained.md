---
UID: NF:printerextension.IPrintSchemaOption.get_Constrained
title: IPrintSchemaOption::get_Constrained (printerextension.h)
description: Gets the constraint setting type for the schema option.
tech.root: print
ms.date: 08/01/2022
keywords: ["IPrintSchemaOption::get_Constrained"]
ms.keywords: Constrained property [Print Devices], Constrained property [Print Devices],IPrintSchemaOption interface, IPrintSchemaOption interface [Print Devices],Constrained property, IPrintSchemaOption.Constrained, IPrintSchemaOption.get_Constrained, IPrintSchemaOption::Constrained, IPrintSchemaOption::get_Constrained, get_Constrained, print.iprintschemaoption_constrained, printerextension/IPrintSchemaOption::Constrained, printerextension/IPrintSchemaOption::get_Constrained
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
 - IPrintSchemaOption::get_Constrained
 - printerextension/IPrintSchemaOption::get_Constrained
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrintSchemaOption::get_Constrained
---

## -description

Gets  the constraint setting type for the schema option.

This property is read-only.

## -parameters

### -param pSetting

Defines the **PrintSchemaConstrainedSetting** parameter *pSetting*.

## -returns

Returns an **HRESULT** value. If the property call was not successful, it returns the appropriate **HRESULT** error code.

## -see-also

[IPrintSchemaOption](./nn-printerextension-iprintschemaoption.md)

[PrintSchemaConstrainedSetting](./ne-printerextension-tagprintschemaconstrainedsetting.md)