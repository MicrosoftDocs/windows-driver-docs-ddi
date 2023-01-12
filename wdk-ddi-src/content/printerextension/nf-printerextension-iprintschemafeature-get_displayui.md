---
UID: NF:printerextension.IPrintSchemaFeature.get_DisplayUI
title: IPrintSchemaFeature::get_DisplayUI (printerextension.h)
description: Gets the setting that indicates whether or not to show the print UI.
tech.root: print
ms.date: 08/01/2022
keywords: ["IPrintSchemaFeature::get_DisplayUI"]
ms.keywords: DisplayUI property [Print Devices], DisplayUI property [Print Devices],IPrintSchemaFeature interface, IPrintSchemaFeature interface [Print Devices],DisplayUI property, IPrintSchemaFeature.DisplayUI, IPrintSchemaFeature.get_DisplayUI, IPrintSchemaFeature::DisplayUI, IPrintSchemaFeature::get_DisplayUI, get_DisplayUI, print.iprintschemafeature_displayui, printerextension/IPrintSchemaFeature::DisplayUI, printerextension/IPrintSchemaFeature::get_DisplayUI
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
 - IPrintSchemaFeature::get_DisplayUI
 - printerextension/IPrintSchemaFeature::get_DisplayUI
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrintSchemaFeature::get_DisplayUI
---

## -description

Gets the setting that indicates whether or not to show the print UI.

This property is read-only.

## -parameters

### -param pbShow

Defines the **BOOL** parameter *pbShow*.

## -returns

Returns an **HRESULT** value. If the property call was not successful, it returns the appropriate **HRESULT** error code.

## -remarks

Note that the **DisplayUI** property  corresponds to the psk:DisplayUI element. If the XML value is unspecified or set to *Show*, then the Print system sets **DisplayUI** to **TRUE.**

## -see-also

[IPrintSchemaFeature](./nn-printerextension-iprintschemafeature.md)