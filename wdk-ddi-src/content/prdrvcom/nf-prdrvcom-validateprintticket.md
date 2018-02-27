---
UID: NF:prdrvcom.ValidatePrintTicket
title: ValidatePrintTicket function
author: windows-driver-content
description: The IPrintOemPrintTicketProvider::ValidatePrintTicket method validates a print ticket.
old-location: print\iprintoemprintticketprovider_validateprintticket.htm
old-project: print
ms.assetid: 359f1a4b-8bcc-4c4a-97d7-6515993765e3
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IPrintOemPrintTicketProvider interface [Print Devices], ValidatePrintTicket method, IPrintOemPrintTicketProvider::ValidatePrintTicket, ValidatePrintTicket, ValidatePrintTicket method [Print Devices], ValidatePrintTicket method [Print Devices], IPrintOemPrintTicketProvider interface, prdrvcom/IPrintOemPrintTicketProvider::ValidatePrintTicket, print.iprintoemprintticketprovider_validateprintticket, print_ticket-package_e7baf633-847b-4e0d-bffb-c723a05b672f.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: prdrvcom.h
req.include-header: Prdrvcom.h
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	prdrvcom.h
apiname:
-	IPrintOemPrintTicketProvider.ValidatePrintTicket
product: Windows
targetos: Windows
req.typenames: SHIMOPTS, *PSHIMOPTS
req.product: Windows 10 or later.
---

# ValidatePrintTicket function


## -description


The <code>IPrintOemPrintTicketProvider::ValidatePrintTicket</code> method validates a print ticket.


## -syntax


````
HRESULT ValidatePrintTicket(
  [in, out] IXMLDOMDocument2 *pPrintTicket
);
````


## -parameters




### -param pBaseTicket

TBD




#### - pPrintTicket [in, out]

A pointer to an input print ticket. When <code>IPrintOemPrintTicketProvider::ValidatePrintTicket</code> successfully returns, <i>pPrintTicket</i> points to a validated print ticket.


## -returns



<code>IPrintOemPrintTicketProvider::ValidatePrintTicket</code> should return S_NO_CONFLICT or S_CONFLICT_RESOLVED if the operation succeeds. Otherwise, this method should return a standard COM error code. Note that Unidrv and Pscript do not consider S_OK to mean successful completion for this method.




## -remarks



If necessary, the <code>IPrintOemPrintTicketProvider::ValidatePrintTicket</code>  method should perform any conflict resolution, by inspecting the settings made in the public and Unidrv-private parts of the print ticket, to ensure that the resulting print ticket is valid, and that all of the constraints are resolved. If any required nodes are not present in the original print ticket, <code>IPrintOemPrintTicketProvider::ValidatePrintTicket</code> can add them to the returned print ticket.




## -see-also

<a href="..\prcomoem\nn-prcomoem-iprintoemprintticketprovider.md">IPrintOemPrintTicketProvider</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintOemPrintTicketProvider::ValidatePrintTicket method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

