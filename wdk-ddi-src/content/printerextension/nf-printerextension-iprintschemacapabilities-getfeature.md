---
UID: NF:printerextension.IPrintSchemaCapabilities.GetFeature
title: IPrintSchemaCapabilities::GetFeature (printerextension.h)
description: Gets a named feature from the PrintCapabilities, by name and full namespace URI.
old-location: print\iprintschemacapabilities_getfeature.htm
tech.root: print
ms.assetid: AC6434F5-0892-4426-98BB-BC02AD17917B
ms.date: 04/20/2018
keywords: ["IPrintSchemaCapabilities::GetFeature"]
ms.keywords: GetFeature, GetFeature method [Print Devices], GetFeature method [Print Devices],IPrintSchemaCapabilities interface, IPrintSchemaCapabilities, IPrintSchemaCapabilities interface [Print Devices],GetFeature method, IPrintSchemaCapabilities.GetFeature, IPrintSchemaCapabilities::GetFeature, print.iprintschemacapabilities_getfeature, printerextension/IPrintSchemaCapabilities::GetFeature
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
 - IPrintSchemaCapabilities::GetFeature
 - printerextension/IPrintSchemaCapabilities::GetFeature
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrintSchemaCapabilities.GetFeature
---

# IPrintSchemaCapabilities::GetFeature


## -description

Gets a named feature from the PrintCapabilities, by name and full namespace URI.

## -parameters

### -param bstrName 

[in]
The base  value of the "name" attribute of the Feature element. For example, for the Print Schema feature, the tag looks like this <psf:Feature name="psk:JobOutputBin">, showing  a base value of "JobOutputBin".

### -param bstrNamespaceUri 

[in]
The namespace URI value of the "name" attribute of the Feature element. For example, for the Print Schema feature, the tag looks like this <psf:Feature name="psk:JobOutputBin">, with a base name value of "JobOutputBin", and the namespace URI of the public Print Schema is "https://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords".
If the feature is not defined in the public Print Schema, then this should be the URI of the private namespace that defines the feature.

### -param ppFeature 

[out, retval]
The returned feature.

## -returns

This method returns an <b>HRESULT</b> value.

## -remarks

When the requested feature, option or property is not found, this method returns S_FALSE and sets a NULL pointer on the output object of the feature, option or property.

So if the <a href="/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschematicket">IPrintSchemaTicket</a> object does not contain the specified feature, option or property, the app must obtain an <a href="/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemacapabilities">IPrintSchemaCapabilities</a> object and query it via <a href="/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprintschemacapabilities-getfeaturebykeyname">IPrintSchemaCapabilities::GetFeatureByKeyName</a> or via <b>IPrintSchemaCapabilities::GetFeature</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemacapabilities">IPrintSchemaCapabilities</a>



<a href="/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemafeature">IPrintSchemaFeature</a>



<a href="/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschematicket">IPrintSchemaTicket</a>