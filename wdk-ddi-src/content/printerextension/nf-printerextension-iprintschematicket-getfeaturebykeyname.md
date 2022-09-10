---
UID: NF:printerextension.IPrintSchemaTicket.GetFeatureByKeyName
title: IPrintSchemaTicket::GetFeatureByKeyName (printerextension.h)
description: Gets a feature from the PrintTicket based on the specified key name.
tech.root: print
ms.date: 08/02/2022
keywords: ["IPrintSchemaTicket::GetFeatureByKeyName"]
ms.keywords: GetFeatureByKeyName, GetFeatureByKeyName method [Print Devices], GetFeatureByKeyName method [Print Devices],IPrintSchemaTicket interface, IPrintSchemaTicket, IPrintSchemaTicket interface [Print Devices],GetFeatureByKeyName method, IPrintSchemaTicket.GetFeatureByKeyName, IPrintSchemaTicket::GetFeatureByKeyName, print.iprintschematicket_getfeaturebykeyname, printerextension/IPrintSchemaTicket::GetFeatureByKeyName
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
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
 - IPrintSchemaTicket::GetFeatureByKeyName
 - printerextension/IPrintSchemaTicket::GetFeatureByKeyName
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrintSchemaTicket::GetFeatureByKeyName
---

## -description

Gets a feature from the PrintTicket based on the specified key name.

## -parameters

### -param bstrKeyName [in]

The key name of the feature.

### -param ppFeature [out, retval]

The returned feature.

## -returns

This method returns an **HRESULT** value.

## -remarks

See [IPrintSchemaCapabilities::GetFeatureByKeyName](./nf-printerextension-iprintschemacapabilities-getfeaturebykeyname.md) for the recognized feature key names, the key names' equivalent public Print Schema feature names, and the supported specialized option types.

When the requested feature, option or property is not found, this method returns S_FALSE and sets a NULL pointer on the output object of the feature, option or property.

So if the [IPrintSchemaTicket](./nn-printerextension-iprintschematicket.md) object does not contain the specified feature, option or property, the app must obtain an [IPrintSchemaCapabilities](./nn-printerextension-iprintschemacapabilities.md) object and query it via **IPrintSchemaCapabilities::GetFeatureByKeyName** or via [IPrintSchemaCapabilities::GetFeature](./nf-printerextension-iprintschemacapabilities-getfeature.md).

## -see-also

[IPrintSchemaCapabilities](./nn-printerextension-iprintschemacapabilities.md)

[IPrintSchemaCapabilities::GetFeature](./nf-printerextension-iprintschemacapabilities-getfeature.md)

[IPrintSchemaCapabilities::GetFeatureByKeyName](./nf-printerextension-iprintschemacapabilities-getfeaturebykeyname.md)

[IPrintSchemaFeature](./nn-printerextension-iprintschemafeature.md)

[IPrintSchemaTicket](./nn-printerextension-iprintschematicket.md)