---
UID: NF:printerextension.IPrinterExtensionAsyncOperation.Cancel
title: IPrinterExtensionAsyncOperation::Cancel method
author: windows-driver-content
description: Cancels the asynchronous operation.
old-location: print\iprinterextensionasyncoperation_cancel.htm
old-project: print
ms.assetid: B5E1F3C4-A131-411B-BBAB-6E8B69433E13
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: Cancel method [Print Devices], Cancel method [Print Devices], IPrinterExtensionAsyncOperation interface, Cancel,IPrinterExtensionAsyncOperation.Cancel, IPrinterExtensionAsyncOperation, IPrinterExtensionAsyncOperation interface [Print Devices], Cancel method, IPrinterExtensionAsyncOperation::Cancel, print.iprinterextensionasyncoperation_cancel, printerextension/IPrinterExtensionAsyncOperation::Cancel
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	IPrinterExtensionAsyncOperation.Cancel
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrinterExtensionAsyncOperation::Cancel method


## -description


Cancels the asynchronous operation.


## -parameters






#### - void

None.


## -returns



This method returns an <b>HRESULT</b> value.




## -remarks



This method guarantees that the callback object will not be invoked. No other form of status is provided, such as a way to check to see if the operation has been canceled.
Also, note that this method does not wait for the cancellation to be processed - it returns immediately.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn265387">IPrinterExtensionAsyncOperation</a>
 

 

