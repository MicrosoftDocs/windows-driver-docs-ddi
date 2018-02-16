---
UID: NF:printerextension.IPrinterExtensionEventArgs.get_Request
title: IPrinterExtensionEventArgs::get_Request method
author: windows-driver-content
description: Gets the IPrinterExtensionRequest object for the current event.
old-location: print\iprinterextensioneventargs_request.htm
old-project: print
ms.assetid: 2F11C510-B649-4DC6-B0BC-89C4159E464C
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: get_Request, IPrinterExtensionEventArgs::get_Request, Request property [Print Devices], IPrinterExtensionEventArgs interface, IPrinterExtensionEventArgs interface [Print Devices], Request property, printerextension/IPrinterExtensionEventArgs::get_Request, print.iprinterextensioneventargs_request, Request property [Print Devices], printerextension/IPrinterExtensionEventArgs::Request, IPrinterExtensionEventArgs, IPrinterExtensionEventArgs.Request
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
-	IPrinterExtensionEventArgs.Request
-	IPrinterExtensionEventArgs.get_Request
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrinterExtensionEventArgs::get_Request method


## -description


Gets the <a href="..\printerextension\nn-printerextension-iprinterextensionrequest.md">IPrinterExtensionRequest</a> object for the current event.

This interface is used to complete or cancel the event.

This property is read-only.


## -syntax


````
HRESULT get_Request(
  [out, retval] IPrinterExtensionRequest **ppRequest
);
````


## -parameters


## -see-also

<a href="..\printerextension\nn-printerextension-iprinterextensioneventargs.md">IPrinterExtensionEventArgs</a>



<a href="..\printerextension\nn-printerextension-iprinterextensionrequest.md">IPrinterExtensionRequest</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterExtensionEventArgs::Request property%20 RELEASE:%20(2/2/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

