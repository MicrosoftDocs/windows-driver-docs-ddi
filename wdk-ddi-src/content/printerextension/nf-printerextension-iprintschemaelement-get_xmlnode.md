---
UID: NF:printerextension.IPrintSchemaElement.get_XmlNode
title: IPrintSchemaElement::get_XmlNode method
author: windows-driver-content
description: Gets the IXMLDOMNode object associated with this item.
old-location: print\iprintschemaelement_xmlnode.htm
old-project: print
ms.assetid: 5E7F2292-1F71-4581-8E34-86F1464EC08F
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrintSchemaElement, IPrintSchemaElement interface [Print Devices], XmlNode property, IPrintSchemaElement.XmlNode, IPrintSchemaElement::get_XmlNode, XmlNode property [Print Devices], XmlNode property [Print Devices], IPrintSchemaElement interface, get_XmlNode, get_XmlNode,IPrintSchemaElement.get_XmlNode, print.iprintschemaelement_xmlnode, printerextension/IPrintSchemaElement::XmlNode, printerextension/IPrintSchemaElement::get_XmlNode
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Printerextension.h
api_name:
-	IPrintSchemaElement.XmlNode
-	IPrintSchemaElement.get_XmlNode
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrintSchemaElement::get_XmlNode method


## -description


Gets the IXMLDOMNode object associated with this item.

This property is read-only.


## -parameters


## -remarks



When you dereference the <i>ppXmlNode</i> parameter (using *ppXmlNode ), you obtain a pointer to an interface of type <b>IUnknown</b>. Use this pointer to  call the <b>QueryInterface</b> method, to access the underlying <a href="http://msdn.microsoft.com/en-us/library/windows/desktop/ms760248(v=vs.85).aspx">IXMLDOMElement</a> object.print.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451256">IPrintSchemaCapabilities</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451270">IPrintSchemaElement</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451398">IPrintSchemaTicket</a>



<a href="https://msdn.microsoft.com/B9A0C9EC-6C37-4C42-A10A-8CEE028C5998">IPrintSchemaTicket::NotifyXmlChanged</a>



<a href="https://msdn.microsoft.com/5556BD5E-6489-4CCF-8C62-DDA53AD9F368">IPrintSchemaTicket_GetCapabilities</a>



<a href="http://msdn.microsoft.com/en-us/library/windows/desktop/ms760248(v=vs.85).aspx">IXMLDOMElement</a>
 

 

