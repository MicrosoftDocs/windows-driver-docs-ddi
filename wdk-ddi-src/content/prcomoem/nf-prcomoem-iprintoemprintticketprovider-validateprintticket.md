---
UID: NF:prcomoem.IPrintOemPrintTicketProvider.ValidatePrintTicket
title: IPrintOemPrintTicketProvider::ValidatePrintTicket (prcomoem.h)
description: The IPrintOemPrintTicketProvider::ValidatePrintTicket method validates a print ticket.
tech.root: print
ms.date: 08/22/2022
keywords: ["IPrintOemPrintTicketProvider::ValidatePrintTicket"]
ms.keywords: IPrintOemPrintTicketProvider interface [Print Devices],ValidatePrintTicket method, IPrintOemPrintTicketProvider.ValidatePrintTicket, IPrintOemPrintTicketProvider::ValidatePrintTicket, ValidatePrintTicket, ValidatePrintTicket method [Print Devices], ValidatePrintTicket method [Print Devices],IPrintOemPrintTicketProvider interface, prcomoem/IPrintOemPrintTicketProvider::ValidatePrintTicket, print.iprintoemprintticketprovider_validateprintticket, print_ticket-package_e7baf633-847b-4e0d-bffb-c723a05b672f.xml
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IPrintOemPrintTicketProvider::ValidatePrintTicket
 - prcomoem/IPrintOemPrintTicketProvider::ValidatePrintTicket
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - prcomoem.h
api_name:
 - IPrintOemPrintTicketProvider::ValidatePrintTicket
---

## -description

The **IPrintOemPrintTicketProvider::ValidatePrintTicket** method validates a print ticket.

## -parameters

### -param pPrintTicket [in, out]

A pointer to an input print ticket. When **IPrintOemPrintTicketProvider::ValidatePrintTicket** successfully returns, *pPrintTicket* points to a validated print ticket.

## -returns

**IPrintOemPrintTicketProvider::ValidatePrintTicket** should return **S_NO_CONFLICT** or **S_CONFLICT_RESOLVED** if the operation succeeds. Otherwise, this method should return a standard COM error code. Note that Unidrv and Pscript do not consider **S_OK** to mean successful completion for this method.

## -remarks

If necessary, the **IPrintOemPrintTicketProvider::ValidatePrintTicket**  method should perform any conflict resolution, by inspecting the settings made in the public and Unidrv-private parts of the print ticket, to ensure that the resulting print ticket is valid, and that all of the constraints are resolved. If any required nodes are not present in the original print ticket, **IPrintOemPrintTicketProvider::ValidatePrintTicket** can add them to the returned print ticket.

## -see-also

[IPrintOemPrintTicketProvider](../nn-prcomoem-iprintoemprintticketprovider.md)
