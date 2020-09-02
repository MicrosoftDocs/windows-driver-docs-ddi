---
UID: NN:printerextension.IPrintSchemaTicket
title: IPrintSchemaTicket (printerextension.h)
description: Provides the primary method to access and validate a PrintTicket.
old-location: print\iprintschematicket_interface.htm
tech.root: print
ms.assetid: 190B0B88-6018-4B43-8699-78427421D6FF
ms.date: 10/19/2018
keywords: ["IPrintSchemaTicket interface"]
ms.keywords: IPrintSchemaTicket, IPrintSchemaTicket interface [Print Devices], IPrintSchemaTicket interface [Print Devices],described, print.iprintschematicket_interface, printerextension/IPrintSchemaTicket
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
 - IPrintSchemaTicket
 - printerextension/IPrintSchemaTicket
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrintSchemaTicket
---

# IPrintSchemaTicket interface


## -description

Provides the primary method to access and validate a PrintTicket.

## -inheritance

The **IPrintSchemaTicket** interface inherits from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemaelement">IPrintSchemaElement</a>. **IPrintSchemaTicket** also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
<li><a href="https://docs.microsoft.com/">Properties</a></li>
</ul>

## -remarks

For C++ clients, to obtain an IXMLDOMDocument2 object for the PrintTicket object, you must first dereference the <i>ppXmlNode</i> parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprintschemaelement-get_xmlnode">XmlNode</a> property (using *ppXmlNode ). This retrieves a pointer to an interface of type <b>IUnknown</b>. Use this pointer to  call the <b>QueryInterface</b> method of the PrintTicket object to access the underlying IXMLDOMDocument2 object.

For C# and JavaScript clients, use printerextension.h GetReadStream or GetWriteStream methods to access a IPrintSchemaElement XmlNode.

## -see-also

[IPrintSchemaAsyncOperationEvent::Completed](https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprintschemaasyncoperationevent-completed)

[IPrintSchemaCapabilities](https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemacapabilities)

[IPrintSchemaElement](https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemaelement)

[IPrintSchemaElement::XmlNode](https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprintschemaelement-get_xmlnode)

