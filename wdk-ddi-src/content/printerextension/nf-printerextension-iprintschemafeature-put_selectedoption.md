---
UID: NF:printerextension.IPrintSchemaFeature.put_SelectedOption
title: IPrintSchemaFeature::put_SelectedOption (printerextension.h)
description: Changes the selected option of the Print Schema Feature element to the specified IPrintSchemaOption element.
tech.root: print
ms.date: 08/03/2022
keywords: ["IPrintSchemaFeature::put_SelectedOption"]
ms.keywords: IPrintSchemaFeature interface [Print Devices],SelectedOption property, IPrintSchemaFeature.SelectedOption, IPrintSchemaFeature.put_SelectedOption, IPrintSchemaFeature::SelectedOption, IPrintSchemaFeature::put_SelectedOption, SelectedOption property [Print Devices], SelectedOption property [Print Devices],IPrintSchemaFeature interface, get_SelectedOption, print.iprintschemafeature_put_selectedoption, printerextension/IPrintSchemaFeature::SelectedOption, printerextension/IPrintSchemaFeature::put_SelectedOption, put_SelectedOption
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
 - IPrintSchemaFeature::put_SelectedOption
 - printerextension/IPrintSchemaFeature::put_SelectedOption
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrintSchemaFeature::put_SelectedOption
---

## -description

Changes the selected option of the Print Schema Feature element to the specified [IPrintSchemaOption](./nn-printerextension-iprintschemaoption.md) element.

This property is write-only.

## -parameters

### -param pOption

Defines the **IPrintSchemaOption** parameter *pOption*.

## -returns

Returns an **HRESULT** value. If the property call was not successful, it returns the appropriate **HRESULT** error code.

## -see-also

[IPrintSchemaFeature](./nn-printerextension-iprintschemafeature.md)

[IPrintSchemaOption](./nn-printerextension-iprintschemaoption.md)