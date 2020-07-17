---
UID: NF:printerextension.IPrintSchemaOption.GetPropertyValue
title: IPrintSchemaOption::GetPropertyValue (printerextension.h)
description: Gets the XML node for the value child element of a Property or a ScoredProperty element with the given name.
old-location: print\iprintschemaoption_getpropertyvalue.htm
tech.root: print
ms.assetid: 6CD5202C-7852-46AA-90ED-3477E6654188
ms.date: 06/25/2020
keywords: ["IPrintSchemaOption::GetPropertyValue"]
ms.keywords: GetPropertyValue, GetPropertyValue method [Print Devices], GetPropertyValue method [Print Devices],IPrintSchemaOption interface, IPrintSchemaOption, IPrintSchemaOption interface [Print Devices],GetPropertyValue method, IPrintSchemaOption.GetPropertyValue, IPrintSchemaOption::GetPropertyValue, print.iprintschemaoption_getpropertyvalue, printerextension/IPrintSchemaOption::GetPropertyValue
f1_keywords:
 - "printerextension/IPrintSchemaOption.GetPropertyValue"
 - "IPrintSchemaOption.GetPropertyValue"
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Printerextension.h
api_name:
- IPrintSchemaOption.GetPropertyValue
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintSchemaOption::GetPropertyValue

## -description

Gets the XML node for the value child element of a Property  or a ScoredProperty element with the given name.

## -parameters

### -param bstrName [in]

The base value of the name attribute of the Property or the ScoredProperty element.

### -param bstrNamespaceUri [in]

The namespace URI value of the name attribute of the Property or the ScoredProperty element.

### -param ppXmlValueNode

#### - ppXmlNodeValue [out, retval]

The XML node for the value child element.

## -returns

Returns an **HRESULT** value. If the method call was not successful,  it returns the appropriate **HRESULT** error code.

## -remarks

When the requested feature, option or property is not found, this method returns S_FALSE and sets a NULL pointer on the output object of the feature, option or property.

If the [IPrintSchemaTicket](https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschematicket) object does not contain the specified feature, option or property, the app must obtain an [IPrintSchemaCapabilities](https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemacapabilities) object and query it via [IPrintSchemaCapabilities::GetFeatureByKeyName](https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprintschemacapabilities-getfeaturebykeyname) or via [IPrintSchemaCapabilities::GetFeature](https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprintschemacapabilities-getfeature).

## -see-also

[IPrintSchemaCapabilities](https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemacapabilities)

[IPrintSchemaOption](https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemaoption)

[IPrintSchemaTicket](https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschematicket)
