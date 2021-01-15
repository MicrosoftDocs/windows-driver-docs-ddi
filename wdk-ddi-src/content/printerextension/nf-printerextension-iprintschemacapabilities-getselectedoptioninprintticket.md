---
UID: NF:printerextension.IPrintSchemaCapabilities.GetSelectedOptionInPrintTicket
title: IPrintSchemaCapabilities::GetSelectedOptionInPrintTicket (printerextension.h)
description: Gets the selected option for a feature in IPrintSchemaTicket.
old-location: print\iprintschemacapabilities_getselectedoptioninprintticket.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["IPrintSchemaCapabilities::GetSelectedOptionInPrintTicket"]
ms.keywords: GetSelectedOptionInPrintTicket, GetSelectedOptionInPrintTicket method [Print Devices], GetSelectedOptionInPrintTicket method [Print Devices],IPrintSchemaCapabilities interface, IPrintSchemaCapabilities, IPrintSchemaCapabilities interface [Print Devices],GetSelectedOptionInPrintTicket method, IPrintSchemaCapabilities.GetSelectedOptionInPrintTicket, IPrintSchemaCapabilities::GetSelectedOptionInPrintTicket, print.iprintschemacapabilities_getselectedoptioninprintticket, printerextension/IPrintSchemaCapabilities::GetSelectedOptionInPrintTicket
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
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
 - IPrintSchemaCapabilities::GetSelectedOptionInPrintTicket
 - printerextension/IPrintSchemaCapabilities::GetSelectedOptionInPrintTicket
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrintSchemaCapabilities::GetSelectedOptionInPrintTicket
---

# IPrintSchemaCapabilities::GetSelectedOptionInPrintTicket


## -description

Gets the selected option for a feature in <a href="/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschematicket">IPrintSchemaTicket</a>.

## -parameters

### -param pFeature 

[in]
The specified feature.

### -param ppOption 

[out, retval]
The returned option.

## -returns

This method returns an <b>HRESULT</b> value.

## -remarks

When the requested feature, option or property is not found, this method returns S_FALSE and sets a NULL pointer on the output object of the feature, option or property.

So if the <a href="/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschematicket">IPrintSchemaTicket</a> object does not contain the specified feature, option or property, the app must obtain an <a href="/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemacapabilities">IPrintSchemaCapabilities</a> object and query it via <a href="/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprintschemacapabilities-getfeaturebykeyname">IPrintSchemaCapabilities::GetFeatureByKeyName</a> or via <a href="/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprintschemacapabilities-getfeature">IPrintSchemaCapabilities::GetFeature</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemacapabilities">IPrintSchemaCapabilities</a>



<a href="/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschematicket">IPrintSchemaTicket</a>

