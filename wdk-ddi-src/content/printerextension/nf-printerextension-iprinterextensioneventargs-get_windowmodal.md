---
UID: NF:printerextension.IPrinterExtensionEventArgs.get_WindowModal
title: IPrinterExtensionEventArgs::get_WindowModal method
author: windows-driver-content
description: Gets the run mode parameter that determines whether or not the printer extension should be run as modal.
old-location: print\iprinterextensioneventargs_windowmodal.htm
old-project: print
ms.assetid: 606FF5E7-CCC1-4227-8917-F5DF3ECB31A6
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: IPrinterExtensionEventArgs, IPrinterExtensionEventArgs.WindowModal, printerextension/IPrinterExtensionEventArgs::WindowModal, print.iprinterextensioneventargs_windowmodal, get_WindowModal, WindowModal property [Print Devices], IPrinterExtensionEventArgs interface [Print Devices], WindowModal property, WindowModal property [Print Devices], IPrinterExtensionEventArgs interface, IPrinterExtensionEventArgs::get_WindowModal, printerextension/IPrinterExtensionEventArgs::get_WindowModal
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
-	IPrinterExtensionEventArgs.WindowModal
-	IPrinterExtensionEventArgs.get_WindowModal
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrinterExtensionEventArgs::get_WindowModal method


## -description


Gets the run mode parameter that determines whether or not the printer extension should be run as modal.

This property is read-only.


## -syntax


````
HRESULT get_WindowModal(
  [out, retval] BOOL *pbModal
);
````


## -parameters


## -see-also

<a href="..\printerextension\nn-printerextension-iprinterextensioneventargs.md">IPrinterExtensionEventArgs</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterExtensionEventArgs::WindowModal property%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

