---
UID: NF:printerextension.IPrinterExtensionEventArgs.get_WindowParent
title: IPrinterExtensionEventArgs::get_WindowParent method
author: windows-driver-content
description: Gets the handle of the parent window.
old-location: print\iprinterextensioneventargs_windowparent.htm
old-project: print
ms.assetid: 23B8E247-C521-4CBD-ABB3-9A10ECAFAE84
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrinterExtensionEventArgs, IPrinterExtensionEventArgs interface [Print Devices], WindowParent property, IPrinterExtensionEventArgs.WindowParent, IPrinterExtensionEventArgs::get_WindowParent, WindowParent property [Print Devices], WindowParent property [Print Devices], IPrinterExtensionEventArgs interface, get_WindowParent, get_WindowParent,IPrinterExtensionEventArgs.get_WindowParent, print.iprinterextensioneventargs_windowparent, printerextension/IPrinterExtensionEventArgs::WindowParent, printerextension/IPrinterExtensionEventArgs::get_WindowParent
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
-	IPrinterExtensionEventArgs.WindowParent
-	IPrinterExtensionEventArgs.get_WindowParent
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrinterExtensionEventArgs::get_WindowParent method


## -description


Gets the handle of the parent window.

This property is read-only.


## -syntax


````
HRESULT get_WindowParent(
  [out, retval] HANDLE *phwndParent
);
````


## -parameters


## -see-also

<a href="..\printerextension\nn-printerextension-iprinterextensioneventargs.md">IPrinterExtensionEventArgs</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterExtensionEventArgs::WindowParent property%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

