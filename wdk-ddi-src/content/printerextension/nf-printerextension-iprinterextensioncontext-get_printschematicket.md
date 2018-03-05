---
UID: NF:printerextension.IPrinterExtensionContext.get_PrintSchemaTicket
title: IPrinterExtensionContext::get_PrintSchemaTicket method
author: windows-driver-content
description: Gets the print ticket that is appropriate for the queue and the activation.
old-location: print\iprinterextensioncontext_printschematicket.htm
old-project: print
ms.assetid: B217DE53-23B9-46BA-8B35-DA869EB9DBDA
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrinterExtensionContext, IPrinterExtensionContext interface [Print Devices], PrintSchemaTicket property, IPrinterExtensionContext.PrintSchemaTicket, IPrinterExtensionContext::get_PrintSchemaTicket, PrintSchemaTicket property [Print Devices], PrintSchemaTicket property [Print Devices], IPrinterExtensionContext interface, get_PrintSchemaTicket, get_PrintSchemaTicket,IPrinterExtensionContext.get_PrintSchemaTicket, print.iprinterextensioncontext_printschematicket, printerextension/IPrinterExtensionContext::PrintSchemaTicket, printerextension/IPrinterExtensionContext::get_PrintSchemaTicket
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Printerextension.h
api_name:
-	IPrinterExtensionContext.PrintSchemaTicket
-	IPrinterExtensionContext.get_PrintSchemaTicket
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrinterExtensionContext::get_PrintSchemaTicket method


## -description


Gets the print ticket that is appropriate for the queue and the activation.

This property is read-only.


## -syntax


````
HRESULT get_PrintSchemaTicket(
  [out, retval] IPrintSchemaTicket **ppTicket
);
````


## -parameters


## -see-also

<a href="..\printerextension\nn-printerextension-iprintschematicket.md">IPrintSchemaTicket</a>



<a href="..\printerextension\nn-printerextension-iprinterextensioncontext.md">IPrinterExtensionContext</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterExtensionContext::PrintSchemaTicket property%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

