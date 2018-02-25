---
UID: NF:printerextension.IPrintSchemaElement.get_XmlNode
title: IPrintSchemaElement::get_XmlNode method
author: windows-driver-content
description: Gets the IXMLDOMNode object associated with this item.
old-location: print\iprintschemaelement_xmlnode.htm
old-project: print
ms.assetid: 5E7F2292-1F71-4581-8E34-86F1464EC08F
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, ., :, E, I, IPrintSchemaElement, IPrintSchemaElement interface [Print Devices], XmlNode property, IPrintSchemaElement.XmlNode, IPrintSchemaElement::get_XmlNode, N, P, S, X, XmlNode property [Print Devices], XmlNode property [Print Devices], IPrintSchemaElement interface, _, a, c, d, e, g, get_XmlNode, get_XmlNode,IPrintSchemaElement.get_XmlNode, h, i, l, m, n, o, print.iprintschemaelement_xmlnode, printerextension/IPrintSchemaElement::XmlNode, printerextension/IPrintSchemaElement::get_XmlNode, r, t"
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
req.lib: printerextension.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Printerextension.h
apiname:
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


## -syntax


````
HRESULT get_XmlNode(
  [out, retval] IXMLDOMNode **ppXmlNode
);
````


## -parameters


## -remarks



When you dereference the <i>ppXmlNode</i> parameter (using *ppXmlNode ), you obtain a pointer to an interface of type <b>IUnknown</b>. Use this pointer to  call the <b>QueryInterface</b> method, to access the underlying <a href="http://msdn.microsoft.com/en-us/library/windows/desktop/ms760248(v=vs.85).aspx">IXMLDOMElement</a> object.print.




## -see-also

<a href="..\printerextension\nn-printerextension-iprintschemacapabilities.md">IPrintSchemaCapabilities</a>



<a href="..\printerextension\nn-printerextension-iprintschematicket.md">IPrintSchemaTicket</a>



<a href="..\printerextension\nn-printerextension-iprintschemaelement.md">IPrintSchemaElement</a>



<a href="https://msdn.microsoft.com/B9A0C9EC-6C37-4C42-A10A-8CEE028C5998">IPrintSchemaTicket::NotifyXmlChanged</a>



<a href="http://msdn.microsoft.com/en-us/library/windows/desktop/ms760248(v=vs.85).aspx">IXMLDOMElement</a>



<a href="https://msdn.microsoft.com/5556BD5E-6489-4CCF-8C62-DDA53AD9F368">IPrintSchemaTicket_GetCapabilities</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintSchemaElement::XmlNode property%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

