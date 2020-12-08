---
UID: NF:printerextension.IPrintSchemaFeature.get_DisplayUI
title: IPrintSchemaFeature::get_DisplayUI (printerextension.h)
description: Gets the setting that indicates whether or not to show the print UI.
old-location: print\iprintschemafeature_displayui.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["IPrintSchemaFeature::get_DisplayUI"]
ms.keywords: DisplayUI property [Print Devices], DisplayUI property [Print Devices],IPrintSchemaFeature interface, IPrintSchemaFeature interface [Print Devices],DisplayUI property, IPrintSchemaFeature.DisplayUI, IPrintSchemaFeature.get_DisplayUI, IPrintSchemaFeature::DisplayUI, IPrintSchemaFeature::get_DisplayUI, get_DisplayUI, print.iprintschemafeature_displayui, printerextension/IPrintSchemaFeature::DisplayUI, printerextension/IPrintSchemaFeature::get_DisplayUI
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
 - IPrintSchemaFeature.DisplayUI
 - IPrintSchemaFeature.get_DisplayUI
---

# IPrintSchemaFeature::get_DisplayUI


## -description

Gets the setting that indicates whether or not to show the print UI.

This property is read-only.

## -parameters

## -remarks

Note that the <b>DisplayUI</b> property  corresponds to the psk:DisplayUI element. If the XML value is unspecified or set to <i>Show</i>, then the Print system sets  <b>DisplayUI</b> to <b>TRUE.</b>

## -see-also

<a href="/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemafeature">IPrintSchemaFeature</a>
