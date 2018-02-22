---
UID: NF:printerextension.IPrintSchemaTicket.NotifyXmlChanged
title: IPrintSchemaTicket::NotifyXmlChanged method
author: windows-driver-content
description: Notifies the print system that the XML DOM object has changed.
old-location: print\iprintschematicket_notifyxmlchanged.htm
old-project: print
ms.assetid: B9A0C9EC-6C37-4C42-A10A-8CEE028C5998
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: IPrintSchemaTicket::NotifyXmlChanged, print.iprintschematicket_notifyxmlchanged, IPrintSchemaTicket, NotifyXmlChanged, NotifyXmlChanged method [Print Devices], IPrintSchemaTicket interface, IPrintSchemaTicket interface [Print Devices], NotifyXmlChanged method, NotifyXmlChanged method [Print Devices], printerextension/IPrintSchemaTicket::NotifyXmlChanged
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
-	IPrintSchemaTicket.NotifyXmlChanged
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrintSchemaTicket::NotifyXmlChanged method


## -description


Notifies the print system that the XML DOM object has changed.


## -syntax


````
HRESULT NotifyXmlChanged(
    None
);
````


## -parameters






#### - None

This method has no parameters.


## -returns



This method returns an HRESULT value.




## -remarks



If the client retrieves the XML DOM object of the PrintTicket by calling <a href="https://msdn.microsoft.com/5E7F2292-1F71-4581-8E34-86F1464EC08F">IPrintSchemaElement::XmlNode</a>, and makes direct modifications to the PrintTicket using XMLDOM APIs, then it is the responsibility of the client to call <b>IPrintSchemaTicket::NotifyXmlChanged</b> to notify the system that the PrintTicket content has been modified.




## -see-also

<a href="..\printerextension\nn-printerextension-iprintschematicket.md">IPrintSchemaTicket</a>



<a href="https://msdn.microsoft.com/5E7F2292-1F71-4581-8E34-86F1464EC08F">IPrintSchemaElement::XmlNode</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintSchemaTicket::NotifyXmlChanged method%20 RELEASE:%20(2/21/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

