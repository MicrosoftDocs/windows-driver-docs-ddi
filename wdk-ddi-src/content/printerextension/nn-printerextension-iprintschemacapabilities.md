---
UID: NN:printerextension.IPrintSchemaCapabilities
title: IPrintSchemaCapabilities (printerextension.h)
description: Provides the primary method to access PrintCapabilities.
old-location: print\iprintschemacapabilities_interface.htm
tech.root: print
ms.assetid: A148C1B4-99A3-4AF3-B2D6-73684978425F
ms.date: 04/20/2018
keywords: ["IPrintSchemaCapabilities interface"]
ms.keywords: IPrintSchemaCapabilities, IPrintSchemaCapabilities interface [Print Devices], IPrintSchemaCapabilities interface [Print Devices],described, print.iprintschemacapabilities_interface, printerextension/IPrintSchemaCapabilities
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
 - IPrintSchemaCapabilities
 - printerextension/IPrintSchemaCapabilities
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrintSchemaCapabilities
---

# IPrintSchemaCapabilities interface


## -description

Provides the primary method to access PrintCapabilities.

## -inheritance

The <b xmlns:loc="https://microsoft.com/wdcml/l10n">IPrintSchemaCapabilities</b> interface inherits from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemaelement">IPrintSchemaElement</a>. <b>IPrintSchemaCapabilities</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
<li><a href="https://docs.microsoft.com/">Properties</a></li>
</ul>

## -remarks

To obtain an IXMLDOMDocument2 object for the PrintCapabilities object, you must first dereference the <i>ppXmlNode</i> parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprintschemaelement-get_xmlnode">XmlNode</a> property (using *ppXmlNode ). This retrieves a pointer to an interface of type <b>IUnknown</b>. Use this pointer to  call the <b>QueryInterface</b> method of the PrintCapabilities object to access the underlying  IXMLDOMDocument2 object.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/print/v4-printer-driver">Developing v4 print drivers</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemaelement">IPrintSchemaElement</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprintschemaelement-get_xmlnode">IPrintSchemaElement::XmlNode</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschematicket">IPrintSchemaTicket</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprintschematicket-getcapabilities">IPrintSchemaTicket_GetCapabilities</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/print/v4-driver-localization">V4 Printer Driver Localization</a>

