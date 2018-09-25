---
UID: NF:printerextension.IPrinterExtensionEventArgs.get_DetailedReasonId
title: IPrinterExtensionEventArgs::get_DetailedReasonId
author: windows-driver-content
description: Gets a more detailed activation reason than what can be retrieved from ReasonId.
old-location: print\iprinterextensioneventargs_detailedreasonid.htm
tech.root: print
ms.assetid: B39DC40A-2B7D-402F-B88C-E6684BF9AA0F
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: DetailedReasonId property [Print Devices], DetailedReasonId property [Print Devices],IPrinterExtensionEventArgs interface, IPrinterExtensionEventArgs interface [Print Devices],DetailedReasonId property, IPrinterExtensionEventArgs.DetailedReasonId, IPrinterExtensionEventArgs.get_DetailedReasonId, IPrinterExtensionEventArgs::DetailedReasonId, IPrinterExtensionEventArgs::get_DetailedReasonId, get_DetailedReasonId, print.iprinterextensioneventargs_detailedreasonid, printerextension/IPrinterExtensionEventArgs::DetailedReasonId, printerextension/IPrinterExtensionEventArgs::get_DetailedReasonId
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrinterExtensionEventArgs::get_DetailedReasonId


## -description


Gets a more detailed activation reason than what can be retrieved from  <a href="https://msdn.microsoft.com/library/windows/hardware/hh973210">ReasonId</a>.

This property is read-only.


## -parameters


## -remarks



The value of <b>DetailedReasonId</b> is always {5D5A1704-DFD1-4181-8EEE-815C86EDAD31}, which indicates that the printer extension was activated as  a result of a Bidi event.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh973207">IPrinterExtensionEventArgs</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh973210">ReasonId</a>
 

 

