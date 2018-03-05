---
UID: NF:printerextension.IPrinterExtensionEventArgs.get_SourceApplication
title: IPrinterExtensionEventArgs::get_SourceApplication method
author: windows-driver-content
description: Gets the name of the application that invoked the printer extension.
old-location: print\iprinterextensioneventargs_sourceapplication.htm
old-project: print
ms.assetid: 98A8427B-24F7-43D2-A0AD-76E3BC085BCA
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrinterExtensionEventArgs, IPrinterExtensionEventArgs interface [Print Devices], SourceApplication property, IPrinterExtensionEventArgs.SourceApplication, IPrinterExtensionEventArgs::get_SourceApplication, SourceApplication property [Print Devices], SourceApplication property [Print Devices], IPrinterExtensionEventArgs interface, get_SourceApplication, get_SourceApplication,IPrinterExtensionEventArgs.get_SourceApplication, print.iprinterextensioneventargs_sourceapplication, printerextension/IPrinterExtensionEventArgs::SourceApplication, printerextension/IPrinterExtensionEventArgs::get_SourceApplication
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
-	IPrinterExtensionEventArgs.SourceApplication
-	IPrinterExtensionEventArgs.get_SourceApplication
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrinterExtensionEventArgs::get_SourceApplication method


## -description


Gets the name of the application that invoked the printer extension.

This property is read-only.


## -syntax


````
HRESULT get_SourceApplication(
  [out, retval] BSTR *pbstrApplication
);
````


## -parameters


## -see-also

<a href="..\printerextension\nn-printerextension-iprinterextensioneventargs.md">IPrinterExtensionEventArgs</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterExtensionEventArgs::SourceApplication property%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

