---
UID: NF:prdrvcom.IPrintTicketProvider2.ValidatePrintTicket
tech.root: print
title: IPrintTicketProvider2::ValidatePrintTicket (prdrvcom.h)
ms.date: 08/31/2022
targetos: Windows
description: The IPrintTicketProvider2::ValidatePrintTicket method validates a print ticket.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: prdrvcom.h
req.idl: 
req.include-header: Prdrvcom.h
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - prdrvcom.h
api_name:
 - IPrintTicketProvider2::ValidatePrintTicket
f1_keywords:
 - IPrintTicketProvider2::ValidatePrintTicket
 - prdrvcom/IPrintTicketProvider2::ValidatePrintTicket
dev_langs:
 - c++
helpviewer_keywords:
 - ValidatePrintTicket
---

## -description

The **IPrintTicketProvider2::ValidatePrintTicket** method validates a print ticket.

## -parameters

### -param pBaseTicket [in, out]

A pointer to an input print ticket. When **IPrintTicketProvider2::ValidatePrintTicket** successfully returns, *pBaseTicket* points to a validated print ticket.

## -returns

**IPrintTicketProvider2::ValidatePrintTicket** should return **S_NO_CONFLICT** or **S_CONFLICT_RESOLVED** if the operation succeeds. Otherwise, this method should return a standard COM error code.

## -remarks

If necessary, the **IPrintTicketProvider2::ValidatePrintTicket** method should perform any conflict resolution, by inspecting the settings made in the public and Unidrv-private parts of the print ticket, to ensure that the resulting print ticket is valid, and that all of the constraints are resolved. If any required nodes are not present in the original print ticket, **IPrintTicketProvider2::ValidatePrintTicket** can add them to the returned print ticket.
