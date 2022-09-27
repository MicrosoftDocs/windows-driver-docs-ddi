---
UID: NF:printerextension.IPrintSchemaFeature.GetOption
title: IPrintSchemaFeature::GetOption (printerextension.h)
description: Gets the option with the given name.
tech.root: print
ms.date: 08/04/2022
keywords: ["IPrintSchemaFeature::GetOption"]
ms.keywords: GetOption, GetOption method [Print Devices], GetOption method [Print Devices],IPrintSchemaFeature interface, IPrintSchemaFeature, IPrintSchemaFeature interface [Print Devices],GetOption method, IPrintSchemaFeature.GetOption, IPrintSchemaFeature::GetOption, print.iprintschemafeature_getoption, printerextension/IPrintSchemaFeature::GetOption
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
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
 - IPrintSchemaFeature::GetOption
 - printerextension/IPrintSchemaFeature::GetOption
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrintSchemaFeature::GetOption
---

## -description

Gets the option with the given name.

## -parameters

### -param bstrName [in]

The name of the option.

### -param bstrNamespaceUri [in]

The namespace URI of the option.

### -param ppOption [out, retval]

The returned option.

## -returns

This method returns an **HRESULT** value, if the call was successful. Otherwise it returns the appropriate error code.

## -remarks

When the requested feature, option or property is not found, this method returns S_FALSE and sets a NULL pointer on the output object of the feature, option or property.

So if the [IPrintSchemaTicket](./nn-printerextension-iprintschematicket.md) object does not contain the specified feature, option or property, the app must obtain an [IPrintSchemaCapabilities](./nn-printerextension-iprintschemacapabilities.md) object and query it via [IPrintSchemaCapabilities::GetFeatureByKeyName](./nf-printerextension-iprintschemacapabilities-getfeaturebykeyname.md) or via [IPrintSchemaCapabilities::GetFeature](./nf-printerextension-iprintschemacapabilities-getfeature.md).

## -see-also

[IPrintSchemaCapabilities](./nn-printerextension-iprintschemacapabilities.md)

[IPrintSchemaFeature](./nn-printerextension-iprintschemafeature.md)

[IPrintSchemaOption](./nn-printerextension-iprintschemaoption.md)

[IPrintSchemaTicket](./nn-printerextension-iprintschematicket.md)