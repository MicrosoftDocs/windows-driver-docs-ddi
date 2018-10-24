---
UID: NF:printerextension.IPrintSchemaTicket.CommitAsync
title: IPrintSchemaTicket::CommitAsync
author: windows-driver-content
description: Gets an asynchronous PrintTicket commit operation context.
old-location: print\iprintschematicket_commitasync.htm
tech.root: print
ms.assetid: CFEDCABF-A875-4A69-954D-267765350E9D
ms.date: 04/20/2018
ms.keywords: CommitAsync, CommitAsync method [Print Devices], CommitAsync method [Print Devices],IPrintSchemaTicket interface, IPrintSchemaTicket, IPrintSchemaTicket interface [Print Devices],CommitAsync method, IPrintSchemaTicket.CommitAsync, IPrintSchemaTicket::CommitAsync, print.iprintschematicket_commitasync, printerextension/IPrintSchemaTicket::CommitAsync
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	printerextension.h
api_name:
-	IPrintSchemaTicket.CommitAsync
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintSchemaTicket::CommitAsync


## -description


Gets an  asynchronous PrintTicket commit operation context.


## -parameters




### -param pPrintTicketCommit [in]

The print ticket to commit.


### -param ppAsyncOperation [out]

The asynchronous commit operation context.


## -returns



This method returns an <b>HRESULT</b> value.




## -remarks



To perform the commit operation, call the <a href="https://msdn.microsoft.com/8AEA34AA-1A5E-43F6-8EE1-B1A078B6AEA3">IPrintSchemaAsyncOperation::Start</a> method to validate the given <i>pPrintTicketCommit</i> and then apply the validated PrintTicket settings to the current PrintTicket object. When the commit operation is completed or if an error occurs during the commit operation, the <a href="https://msdn.microsoft.com/B1599F21-D6DD-497D-9CD8-6C637ABAA33A">IPrintSchemaAsyncOperationEvent::Completed</a> event is fired.




## -see-also




<a href="https://msdn.microsoft.com/8AEA34AA-1A5E-43F6-8EE1-B1A078B6AEA3">IPrintSchemaAsyncOperation::Start</a>



<a href="https://msdn.microsoft.com/B1599F21-D6DD-497D-9CD8-6C637ABAA33A">IPrintSchemaAsyncOperationEvent::Completed</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451398">IPrintSchemaTicket</a>
 

 

