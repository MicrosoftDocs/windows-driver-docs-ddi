---
UID: NF:printerextension.IPrinterExtensionEventArgs.get_DetailedReasonId
title: IPrinterExtensionEventArgs::get_DetailedReasonId method
author: windows-driver-content
description: Gets a more detailed activation reason than what can be retrieved from ReasonId.
old-location: print\iprinterextensioneventargs_detailedreasonid.htm
old-project: print
ms.assetid: B39DC40A-2B7D-402F-B88C-E6684BF9AA0F
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DetailedReasonId property [Print Devices], DetailedReasonId property [Print Devices], IPrinterExtensionEventArgs interface, IPrinterExtensionEventArgs, IPrinterExtensionEventArgs interface [Print Devices], DetailedReasonId property, IPrinterExtensionEventArgs.DetailedReasonId, IPrinterExtensionEventArgs::get_DetailedReasonId, get_DetailedReasonId, get_DetailedReasonId,IPrinterExtensionEventArgs.get_DetailedReasonId, print.iprinterextensioneventargs_detailedreasonid, printerextension/IPrinterExtensionEventArgs::DetailedReasonId, printerextension/IPrinterExtensionEventArgs::get_DetailedReasonId
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
-	IPrinterExtensionEventArgs.DetailedReasonId
-	IPrinterExtensionEventArgs.get_DetailedReasonId
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrinterExtensionEventArgs::get_DetailedReasonId method


## -description


Gets a more detailed activation reason than what can be retrieved from  <a href="https://msdn.microsoft.com/library/windows/hardware/hh973210">ReasonId</a>.

This property is read-only.


## -parameters


## -remarks



The value of <b>DetailedReasonId</b> is always {5D5A1704-DFD1-4181-8EEE-815C86EDAD31}, which indicates that the printer extension was activated as  a result of a Bidi event.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh973207">IPrinterExtensionEventArgs</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh973210">ReasonId</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterExtensionEventArgs::DetailedReasonId property%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

