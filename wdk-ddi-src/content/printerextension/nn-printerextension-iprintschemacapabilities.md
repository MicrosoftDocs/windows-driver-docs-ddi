---
UID: NN:printerextension.IPrintSchemaCapabilities
title: IPrintSchemaCapabilities (printerextension.h)
description: Provides the primary method to access PrintCapabilities.
tech.root: print
ms.date: 06/11/2021
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

The **IPrintSchemaCapabilities** interface inherits from [IPrintSchemaElement](./nn-printerextension-iprintschemaelement.md).

## -remarks

To obtain an **IXMLDOMDocument2** object for the PrintCapabilities object, you must first dereference the *ppXmlNode* parameter of the [XmlNode](./nf-printerextension-iprintschemaelement-get_xmlnode.md) property (using *ppXmlNode ). This retrieves a pointer to an interface of type **IUnknown**. 

Use this pointer to  call the **QueryInterface** method of the PrintCapabilities object to access the underlying **IXMLDOMDocument2** object.

## -see-also

[Developing v4 print drivers](/windows-hardware/drivers/print/v4-printer-driver)

[IPrintSchemaElement](./nn-printerextension-iprintschemaelement.md)

[IPrintSchemaElement::XmlNode](./nf-printerextension-iprintschemaelement-get_xmlnode.md)

[IPrintSchemaTicket](./nn-printerextension-iprintschematicket.md)

[IPrintSchemaTicket_GetCapabilities](./nf-printerextension-iprintschematicket-getcapabilities.md)

[V4 Printer Driver Localization](/windows-hardware/drivers/print/v4-driver-localization)