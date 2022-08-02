---
UID: NF:printerextension.IPrintSchemaCapabilities.GetFeatureByKeyName
title: IPrintSchemaCapabilities::GetFeatureByKeyName (printerextension.h)
description: Gets a feature from the PrintCapabilities based on a given key name.
tech.root: print
ms.date: 08/02/2022
keywords: ["IPrintSchemaCapabilities::GetFeatureByKeyName"]
ms.keywords: GetFeatureByKeyName, GetFeatureByKeyName method [Print Devices], GetFeatureByKeyName method [Print Devices],IPrintSchemaCapabilities interface, IPrintSchemaCapabilities, IPrintSchemaCapabilities interface [Print Devices],GetFeatureByKeyName method, IPrintSchemaCapabilities.GetFeatureByKeyName, IPrintSchemaCapabilities::GetFeatureByKeyName, print.iprintschemacapabilities_getfeaturebykeyname, printerextension/IPrintSchemaCapabilities::GetFeatureByKeyName
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
 - IPrintSchemaCapabilities::GetFeatureByKeyName
 - printerextension/IPrintSchemaCapabilities::GetFeatureByKeyName
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrintSchemaCapabilities::GetFeatureByKeyName
---

## -description

Gets a feature from the PrintCapabilities based on a given key name.

## -parameters

### -param bstrKeyName [in]

The key name of the feature.

### -param ppFeature [out, retval]

The returned feature.

## -returns

This method returns an **HRESULT** value.

## -remarks

Only the following feature key names are recognized. The key names are equivalent to public Print Schema feature names as shown in the following table. The table also shows the features that have specialized option types (by default the option type is [IPrintSchemaOption](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemaoption)).

| Name | Print schema feature public name | Specialized option type |
|--|--|--|
| DocumentBinding | DocumentBinding or JobBindAllDocuments |  |
| DocumentCollate | DocumentCollate |  |
| DocumentDuplex | JobDuplexAllDocumentsContiguously |  |
| DocumentHolePunch | DocumentHolePunch or JobHolePunch |  |
| DocumentInputBin | JobInputBin, DocumentInputBin or PageInputBin |  |
| DocumentNUp | JobNUpAllDocumentsContiguously | [IPrintSchemaNUpOption](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemanupoption) |
| DocumentStaple | JobStapleAllDocuments or DocumentStaple |  |
| PageMediaSize | PageMediaSize | [IPrintSchemaPageMediaSizeOption](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemapagemediasizeoption) |
| PageMediaType | PageMediaType |  |
| PageOrientation | PageOrientation |  |
| PageOutputColor | PageOutputColor |  |
| PageOutputQuality | PageOutputQuality |  |

When the requested feature, option or property is not found, this method returns S_FALSE and sets a NULL pointer on the output object of the feature, option or property.

So if the [IPrintSchemaTicket](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschematicket) object does not contain the specified feature, option or property, the app must obtain an [IPrintSchemaCapabilities](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemacapabilities) object and query it via **IPrintSchemaCapabilities::GetFeatureByKeyName** or via [IPrintSchemaCapabilities::GetFeature](/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprintschemacapabilities-getfeature).

## -see-also

[IPrintSchemaCapabilities](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemacapabilities)

[IPrintSchemaNUpOption](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemanupoption)

[IPrintSchemaOption](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemaoption)

[IPrintSchemaPageMediaSizeOption](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemapagemediasizeoption)
