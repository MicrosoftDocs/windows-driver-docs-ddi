---
UID: NF:printerextension.IPrinterExtensionManager.EnableEvents
title: IPrinterExtensionManager::EnableEvents method
author: windows-driver-content
description: The EnableEvents method allows events to be generated for the specified printer driver until DisableEvents is called.
old-location: print\iprinterextensionmanager_enableevents.htm
old-project: print
ms.assetid: 8DF89C18-10CA-4E8B-8E2A-B373C80F7B39
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: printerextension/IPrinterExtensionManager::EnableEvents, EnableEvents method [Print Devices], IPrinterExtensionManager, IPrinterExtensionManager interface [Print Devices], EnableEvents method, EnableEvents, IPrinterExtensionManager::EnableEvents, EnableEvents method [Print Devices], IPrinterExtensionManager interface, print.iprinterextensionmanager_enableevents
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
-	IPrinterExtensionManager.EnableEvents
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrinterExtensionManager::EnableEvents method


## -description


The EnableEvents method allows events to be generated for the specified printer driver until  <a href="https://msdn.microsoft.com/library/windows/hardware/hh406703">DisableEvents</a> is called. 


## -syntax


````
HRESULT EnableEvents(
  [in] GUID printerDriverId
);
````


## -parameters




### -param printerDriverId [in]

The GUID representing the specified driver for which to enable events. This GUID is specified in the INF file, and is also specified by the manifest file directive 'PrinterDriverID'.


## -returns


This method returns an <b>HRESULT</b> value.

The printer extension should call this method when it is launched so that driver events are generated for it to consume.



## -remarks


In the case of a driver event like, for example, Print Preferences or Printer Notifications, the app is expected to call <b>EnableEvents</b>. But if the app doesn't call <b>EnableEvents</b> within 30s, the print system assumes that a UI was  called but it's not being responsive so a standard UI is displayed instead.



## -see-also

<a href="https://msdn.microsoft.com/918AE3F6-2AC4-42AD-9581-E87AD7E79BAD">IPrinterExtensionManager</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterExtensionManager::EnableEvents method%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

