---
UID: NF:printerextension.IPrintSchemaTicket.GetFeature
title: IPrintSchemaTicket::GetFeature (printerextension.h)
description: Gets a named feature from the PrintTicket, by name and full namespace URI.
old-location: print\iprintschematicket_getfeature.htm
tech.root: print
ms.assetid: 2E65BDF2-9539-402B-AF19-8CBC84F9C018
ms.date: 04/20/2018
keywords: ["IPrintSchemaTicket::GetFeature"]
ms.keywords: GetFeature, GetFeature method [Print Devices], GetFeature method [Print Devices],IPrintSchemaTicket interface, IPrintSchemaTicket, IPrintSchemaTicket interface [Print Devices],GetFeature method, IPrintSchemaTicket.GetFeature, IPrintSchemaTicket::GetFeature, print.iprintschematicket_getfeature, printerextension/IPrintSchemaTicket::GetFeature
f1_keywords:
 - "printerextension/IPrintSchemaTicket.GetFeature"
 - "IPrintSchemaTicket.GetFeature"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Printerextension.h
api_name:
- IPrintSchemaTicket.GetFeature
targetos: Windows
req.typenames: 
---

# IPrintSchemaTicket::GetFeature


## -description


Gets a named feature from the PrintTicket, by name and full namespace URI.


## -parameters




### -param bstrName 
[in]
The base name of the <b>name</b> attribute value of the feature element.
For example, for the Print Schema feature <psf:Feature name="psk:JobOutputBin">, the base name of the feature is "JobOutputBin".


### -param bstrNamespaceUri 
[in]
The namespace URI of the <b>name</b> attribute value of the feature element.
For example, the namespace URI of the public Print Schema feature "JobOutputBin" is "https://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords".
If the feature is not defined in the public Print Schema, then this should be the URI of the private namespace defining the feature.


### -param ppFeature 
[out, retval]
The returned feature.


## -returns



This method returns an <b>HRESULT</b> value.




## -remarks



When the requested feature, option or property is not found, this method returns S_FALSE and sets a NULL pointer on the output object of the feature, option or property.

So if the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschematicket">IPrintSchemaTicket</a> object does not contain the specified feature, option or property, the app must obtain an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemacapabilities">IPrintSchemaCapabilities</a> object and query it via <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprintschemacapabilities-getfeaturebykeyname">IPrintSchemaCapabilities::GetFeatureByKeyName</a> or via <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprintschemacapabilities-getfeature">IPrintSchemaCapabilities::GetFeature</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemacapabilities">IPrintSchemaCapabilities</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprintschemacapabilities-getfeature">IPrintSchemaCapabilities::GetFeature</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprintschemacapabilities-getfeaturebykeyname">IPrintSchemaCapabilities::GetFeatureByKeyName</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemafeature">IPrintSchemaFeature</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschematicket">IPrintSchemaTicket</a>
 

 

