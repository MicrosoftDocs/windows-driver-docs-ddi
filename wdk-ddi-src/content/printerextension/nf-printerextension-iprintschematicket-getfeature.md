---
UID: NF:printerextension.IPrintSchemaTicket.GetFeature
title: IPrintSchemaTicket::GetFeature (printerextension.h)
description: Gets a named feature from the PrintTicket, by name and full namespace URI.
tech.root: print
ms.date: 08/02/2022
keywords: ["IPrintSchemaTicket::GetFeature"]
ms.keywords: GetFeature, GetFeature method [Print Devices], GetFeature method [Print Devices],IPrintSchemaTicket interface, IPrintSchemaTicket, IPrintSchemaTicket interface [Print Devices],GetFeature method, IPrintSchemaTicket.GetFeature, IPrintSchemaTicket::GetFeature, print.iprintschematicket_getfeature, printerextension/IPrintSchemaTicket::GetFeature
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
 - IPrintSchemaTicket::GetFeature
 - printerextension/IPrintSchemaTicket::GetFeature
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrintSchemaTicket::GetFeature
---

## -description

Gets a named feature from the PrintTicket, by name and full namespace URI.

## -parameters

### -param bstrName [in]

The base name of the **name** attribute value of the feature element.
For example, for the Print Schema feature <psf:Feature name="psk:JobOutputBin">, the base name of the feature is "JobOutputBin".

### -param bstrNamespaceUri [in]

The namespace URI of the **name** attribute value of the feature element.
For example, the namespace URI of the public Print Schema feature "JobOutputBin" is "https://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords".
If the feature is not defined in the public Print Schema, then this should be the URI of the private namespace defining the feature.

### -param ppFeature [out, retval]

The returned feature.

## -returns

This method returns an **HRESULT** value.

## -remarks

When the requested feature, option or property is not found, this method returns S_FALSE and sets a NULL pointer on the output object of the feature, option or property.

So if the [IPrintSchemaTicket](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschematicket) object does not contain the specified feature, option or property, the app must obtain an [IPrintSchemaCapabilities](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemacapabilities) object and query it via [IPrintSchemaCapabilities::GetFeatureByKeyName](/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprintschemacapabilities-getfeaturebykeyname) or via [IPrintSchemaCapabilities::GetFeature](/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprintschemacapabilities-getfeature).

## -see-also

[IPrintSchemaCapabilities](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemacapabilities)

[IPrintSchemaCapabilities::GetFeature](/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprintschemacapabilities-getfeature)

[IPrintSchemaCapabilities::GetFeatureByKeyName](/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprintschemacapabilities-getfeaturebykeyname)

[IPrintSchemaFeature](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemafeature)

[IPrintSchemaTicket](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschematicket)
