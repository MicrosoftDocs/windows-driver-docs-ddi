---
UID: NF:printerextension.IPrintSchemaElement.get_XmlNode
title: IPrintSchemaElement::get_XmlNode (printerextension.h)
description: Gets the IXMLDOMNode object associated with this item.
old-location: print\iprintschemaelement_xmlnode.htm
tech.root: print
ms.assetid: 5E7F2292-1F71-4581-8E34-86F1464EC08F
ms.date: 04/20/2018
keywords: ["IPrintSchemaElement::get_XmlNode"]
ms.keywords: IPrintSchemaElement interface [Print Devices],XmlNode property, IPrintSchemaElement.XmlNode, IPrintSchemaElement.get_XmlNode, IPrintSchemaElement::XmlNode, IPrintSchemaElement::get_XmlNode, XmlNode property [Print Devices], XmlNode property [Print Devices],IPrintSchemaElement interface, get_XmlNode, print.iprintschemaelement_xmlnode, printerextension/IPrintSchemaElement::XmlNode, printerextension/IPrintSchemaElement::get_XmlNode
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
 - IPrintSchemaElement.XmlNode
 - IPrintSchemaElement.get_XmlNode
---

# IPrintSchemaElement::get_XmlNode


## -description

Gets the IXMLDOMNode object associated with this item.

This property is read-only.

## -parameters

## -remarks

When you dereference the <i>ppXmlNode</i> parameter (using *ppXmlNode ), you obtain a pointer to an interface of type <b>IUnknown</b>. Use this pointer to  call the <b>QueryInterface</b> method, to access the underlying <a href="/previous-versions/windows/desktop/ms760248(v=vs.85)">IXMLDOMElement</a> object.print.

## -see-also

<a href="/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemacapabilities">IPrintSchemaCapabilities</a>



<a href="/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschemaelement">IPrintSchemaElement</a>



<a href="/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprintschematicket">IPrintSchemaTicket</a>



<a href="/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprintschematicket-notifyxmlchanged">IPrintSchemaTicket::NotifyXmlChanged</a>



<a href="/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprintschematicket-getcapabilities">IPrintSchemaTicket_GetCapabilities</a>



<a href="/previous-versions/windows/desktop/ms760248(v=vs.85)">IXMLDOMElement</a>