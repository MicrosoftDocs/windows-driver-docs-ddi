---
UID: NF:printerextension.IPrintSchemaTicket.NotifyXmlChanged
title: IPrintSchemaTicket::NotifyXmlChanged (printerextension.h)
description: Notifies the print system that the XML DOM object has changed.
tech.root: print
ms.date: 08/02/2022
keywords: ["IPrintSchemaTicket::NotifyXmlChanged"]
ms.keywords: IPrintSchemaTicket, IPrintSchemaTicket interface [Print Devices],NotifyXmlChanged method, IPrintSchemaTicket.NotifyXmlChanged, IPrintSchemaTicket::NotifyXmlChanged, NotifyXmlChanged, NotifyXmlChanged method [Print Devices], NotifyXmlChanged method [Print Devices],IPrintSchemaTicket interface, print.iprintschematicket_notifyxmlchanged, printerextension/IPrintSchemaTicket::NotifyXmlChanged
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
 - IPrintSchemaTicket::NotifyXmlChanged
 - printerextension/IPrintSchemaTicket::NotifyXmlChanged
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrintSchemaTicket::NotifyXmlChanged
---

## -description

Notifies the print system that the XML DOM object has changed.

## -returns

This method returns an **HRESULT** value.

## -remarks

If the client retrieves the XML DOM object of the PrintTicket by calling [IPrintSchemaElement::XmlNode](./nf-printerextension-iprintschemaelement-get_xmlnode.md), and makes direct modifications to the PrintTicket using XMLDOM APIs, then it is the responsibility of the client to call **IPrintSchemaTicket::NotifyXmlChanged** to notify the system that the PrintTicket content has been modified.

## -see-also

[IPrintSchemaElement::XmlNode](./nf-printerextension-iprintschemaelement-get_xmlnode.md)

[IPrintSchemaTicket](./nn-printerextension-iprintschematicket.md)