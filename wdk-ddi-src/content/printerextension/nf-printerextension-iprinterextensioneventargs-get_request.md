---
UID: NF:printerextension.IPrinterExtensionEventArgs.get_Request
title: IPrinterExtensionEventArgs::get_Request method
author: windows-driver-content
description: Gets the IPrinterExtensionRequest object for the current event.
old-location: print\iprinterextensioneventargs_request.htm
old-project: print
ms.assetid: 2F11C510-B649-4DC6-B0BC-89C4159E464C
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrinterExtensionEventArgs, IPrinterExtensionEventArgs interface [Print Devices], Request property, IPrinterExtensionEventArgs.Request, IPrinterExtensionEventArgs::get_Request, Request property [Print Devices], Request property [Print Devices], IPrinterExtensionEventArgs interface, get_Request, get_Request,IPrinterExtensionEventArgs.get_Request, print.iprinterextensioneventargs_request, printerextension/IPrinterExtensionEventArgs::Request, printerextension/IPrinterExtensionEventArgs::get_Request
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



 

 


