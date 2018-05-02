---
UID: NF:prcomoem.IPrintOemPrintTicketProvider.ValidatePrintTicket
title: IPrintOemPrintTicketProvider::ValidatePrintTicket
author: windows-driver-content
description: The IPrintOemPrintTicketProvider::ValidatePrintTicket method validates a print ticket.
old-location: print\iprintoemprintticketprovider_validateprintticket.htm
old-project: print
ms.assetid: 359f1a4b-8bcc-4c4a-97d7-6515993765e3
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: IPrintOemPrintTicketProvider interface [Print Devices],ValidatePrintTicket method, IPrintOemPrintTicketProvider.ValidatePrintTicket, IPrintOemPrintTicketProvider::ValidatePrintTicket, ValidatePrintTicket, ValidatePrintTicket method [Print Devices], ValidatePrintTicket method [Print Devices],IPrintOemPrintTicketProvider interface, prcomoem/IPrintOemPrintTicketProvider::ValidatePrintTicket, print.iprintoemprintticketprovider_validateprintticket, print_ticket-package_e7baf633-847b-4e0d-bffb-c723a05b672f.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: prcomoem.h
req.include-header: Prcomoem.h
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
-	prcomoem.h
api_name:
-	IPrintOemPrintTicketProvider.ValidatePrintTicket
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemPrintTicketProvider::ValidatePrintTicket


## -description


The <code>IPrintOemPrintTicketProvider::ValidatePrintTicket</code> method validates a print ticket.


## -parameters




### -param pPrintTicket [in, out]

A pointer to an input print ticket. When <code>IPrintOemPrintTicketProvider::ValidatePrintTicket</code> successfully returns, <i>pPrintTicket</i> points to a validated print ticket.


## -returns



<code>IPrintOemPrintTicketProvider::ValidatePrintTicket</code> should return S_NO_CONFLICT or S_CONFLICT_RESOLVED if the operation succeeds. Otherwise, this method should return a standard COM error code. Note that Unidrv and Pscript do not consider S_OK to mean successful completion for this method.




## -remarks



If necessary, the <code>IPrintOemPrintTicketProvider::ValidatePrintTicket</code>  method should perform any conflict resolution, by inspecting the settings made in the public and Unidrv-private parts of the print ticket, to ensure that the resulting print ticket is valid, and that all of the constraints are resolved. If any required nodes are not present in the original print ticket, <code>IPrintOemPrintTicketProvider::ValidatePrintTicket</code> can add them to the returned print ticket.




## -see-also




<a href="https://msdn.microsoft.com/a32b5ec9-b4f2-4f33-879d-252806bd34ed">IPrintOemPrintTicketProvider</a>
 

 


