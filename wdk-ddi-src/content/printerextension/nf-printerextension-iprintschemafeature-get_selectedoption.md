---
UID: NF:printerextension.IPrintSchemaFeature.get_SelectedOption
title: IPrintSchemaFeature::get_SelectedOption (printerextension.h)
description: Gets an IPrintSchemaOption representing the selected option.
tech.root: print
ms.date: 08/01/2022
keywords: ["IPrintSchemaFeature::get_SelectedOption"]
ms.keywords: IPrintSchemaFeature interface [Print Devices],SelectedOption property, IPrintSchemaFeature.SelectedOption, IPrintSchemaFeature.get_SelectedOption, IPrintSchemaFeature::SelectedOption, IPrintSchemaFeature::get_SelectedOption, SelectedOption property [Print Devices], SelectedOption property [Print Devices],IPrintSchemaFeature interface, get_SelectedOption, print.iprintschemafeature_selectedoption, printerextension/IPrintSchemaFeature::SelectedOption, printerextension/IPrintSchemaFeature::get_SelectedOption
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
 - IPrintSchemaFeature::get_SelectedOption
 - printerextension/IPrintSchemaFeature::get_SelectedOption
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrintSchemaFeature::get_SelectedOption
---

## -description

Gets an [IPrintSchemaOption](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemaoption) representing the selected option.

This property is read-only.

## -parameters

### -param ppOption

Defines the **IPrintSchemaOption** parameter *ppOption*.

## -returns

Returns an **HRESULT** value. If the property call was not successful, it returns the appropriate **HRESULT** error code.

## -see-also

[IPrintSchemaFeature](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemafeature)

[IPrintSchemaOption](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemaoption)

[IPrintSchemaTicket_GetCapabilities](/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprintschematicket-getcapabilities)
