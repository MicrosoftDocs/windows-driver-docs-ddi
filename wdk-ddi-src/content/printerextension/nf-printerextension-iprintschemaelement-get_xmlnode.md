---
UID: NF:printerextension.IPrintSchemaElement.get_XmlNode
title: IPrintSchemaElement::get_XmlNode (printerextension.h)
description: Gets the IXMLDOMNode object associated with this item.
tech.root: print
ms.date: 08/01/2022
keywords: ["IPrintSchemaElement::get_XmlNode"]
ms.keywords: IPrintSchemaElement interface [Print Devices],XmlNode property, IPrintSchemaElement.XmlNode, IPrintSchemaElement.get_XmlNode, IPrintSchemaElement::XmlNode, IPrintSchemaElement::get_XmlNode, XmlNode property [Print Devices], XmlNode property [Print Devices],IPrintSchemaElement interface, get_XmlNode, print.iprintschemaelement_xmlnode, printerextension/IPrintSchemaElement::XmlNode, printerextension/IPrintSchemaElement::get_XmlNode
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
 - IPrintSchemaElement::get_XmlNode
 - printerextension/IPrintSchemaElement::get_XmlNode
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrintSchemaElement::get_XmlNode
---

## -description

Gets the IXMLDOMNode object associated with this item.

This property is read-only.

## -parameters

### -param ppXmlNode

Defines the **IUnknown** parameter *ppXmlNode*.

## -returns

Returns an **HRESULT** value. If the property call was not successful, it returns the appropriate **HRESULT** error code.

## -remarks

When you dereference the *ppXmlNode* parameter (using *ppXmlNode ), you obtain a pointer to an interface of type **IUnknown**. Use this pointer to  call the **QueryInterface** method, to access the underlying [IXMLDOMElement](/previous-versions/windows/desktop/ms760248(v=vs.85)) object.print.

## -see-also

[IPrintSchemaCapabilities](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemacapabilities)

[IPrintSchemaElement](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemaelement)

[IPrintSchemaTicket](/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschematicket)

[IPrintSchemaTicket::NotifyXmlChanged](/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprintschematicket-notifyxmlchanged)

[IPrintSchemaTicket_GetCapabilities](/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprintschematicket-getcapabilities)

[IXMLDOMElement](/previous-versions/windows/desktop/ms760248(v=vs.85))
