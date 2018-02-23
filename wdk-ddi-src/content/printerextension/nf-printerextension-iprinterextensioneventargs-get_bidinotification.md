---
UID: NF:printerextension.IPrinterExtensionEventArgs.get_BidiNotification
title: IPrinterExtensionEventArgs::get_BidiNotification method
author: windows-driver-content
description: Gets the text of the bidirectional communication (Bidi) notification, if applicable.
old-location: print\iprinterextensioneventargs_bidinotification.htm
old-project: print
ms.assetid: 8AAC657A-218E-41CF-AE89-0199A5B35280
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: IPrinterExtensionEventArgs, get_BidiNotification, IPrinterExtensionEventArgs interface [Print Devices], BidiNotification property, IPrinterExtensionEventArgs.BidiNotification, print.iprinterextensioneventargs_bidinotification, BidiNotification property [Print Devices], IPrinterExtensionEventArgs interface, BidiNotification property [Print Devices], printerextension/IPrinterExtensionEventArgs::get_BidiNotification, printerextension/IPrinterExtensionEventArgs::BidiNotification, IPrinterExtensionEventArgs::get_BidiNotification
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
-	IPrinterExtensionEventArgs.BidiNotification
-	IPrinterExtensionEventArgs.get_BidiNotification
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrinterExtensionEventArgs::get_BidiNotification method


## -description


Gets the text of the bidirectional communication (Bidi) notification, if applicable.

This property is read-only.


## -syntax


````
HRESULT get_BidiNotification(
  [out, retval] BSTR *pbstrBidiNotification
);
````


## -parameters


## -see-also

<a href="..\printerextension\nn-printerextension-iprinterextensioneventargs.md">IPrinterExtensionEventArgs</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterExtensionEventArgs::BidiNotification property%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

