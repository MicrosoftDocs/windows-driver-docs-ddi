---
UID: NN:printerextension.IPrintSchemaTicket
title: IPrintSchemaTicket (printerextension.h)
description: Provides the primary method to access and validate a PrintTicket.
old-location: print\iprintschematicket_interface.htm
tech.root: print
ms.date: 06/11/2021
keywords: ["IPrintSchemaTicket interface"]
ms.keywords: IPrintSchemaTicket, IPrintSchemaTicket interface [Print Devices], IPrintSchemaTicket interface [Print Devices],described, print.iprintschematicket_interface, printerextension/IPrintSchemaTicket
req.header: printerextension.h
req.include-header: Printerextension.h
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

The **IPrintSchemaTicket** interface inherits from [IPrintSchemaElement](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemaelement).

## -remarks

For C++ clients, to obtain an **IXMLDOMDocument2** object for the PrintTicket object, you must first dereference the *ppXmlNode* parameter of the [XmlNode](/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprintschemaelement-get_xmlnode) property (using *ppXmlNode ). This retrieves a pointer to an interface of type **IUnknown**. Use this pointer to  call the **QueryInterface** method of the PrintTicket object to access the underlying IXMLDOMDocument2 object.

For C# and JavaScript clients, use printerextension.h GetReadStream or GetWriteStream methods to access a IPrintSchemaElement XmlNode.

## -see-also

[IPrintSchemaAsyncOperationEvent::Completed](./nf-printerextension-iprintschemaasyncoperationevent-completed.md)

[IPrintSchemaCapabilities](./nn-printerextension-iprintschemacapabilities.md)

[IPrintSchemaElement](./nn-printerextension-iprintschemaelement.md)

[IPrintSchemaElement::XmlNode](./nf-printerextension-iprintschemaelement-get_xmlnode.md)
