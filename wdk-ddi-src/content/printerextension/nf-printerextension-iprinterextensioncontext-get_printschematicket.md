---
UID: NF:printerextension.IPrinterExtensionContext.get_PrintSchemaTicket
title: IPrinterExtensionContext::get_PrintSchemaTicket (printerextension.h)
description: Gets the print ticket that is appropriate for the queue and the activation.
old-location: print\iprinterextensioncontext_printschematicket.htm
tech.root: print
ms.assetid: B217DE53-23B9-46BA-8B35-DA869EB9DBDA
ms.date: 10/19/2018
ms.keywords: IPrinterExtensionContext interface [Print Devices],PrintSchemaTicket property, IPrinterExtensionContext.PrintSchemaTicket, IPrinterExtensionContext.get_PrintSchemaTicket, IPrinterExtensionContext::PrintSchemaTicket, IPrinterExtensionContext::get_PrintSchemaTicket, PrintSchemaTicket property [Print Devices], PrintSchemaTicket property [Print Devices],IPrinterExtensionContext interface, get_PrintSchemaTicket, print.iprinterextensioncontext_printschematicket, printerextension/IPrinterExtensionContext::PrintSchemaTicket, printerextension/IPrinterExtensionContext::get_PrintSchemaTicket
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
-	IPrinterExtensionContext.PrintSchemaTicket
-	IPrinterExtensionContext.get_PrintSchemaTicket
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrinterExtensionContext::get_PrintSchemaTicket


## -description


Gets the print ticket that is appropriate for the queue and the activation.

This property is read-only.


## -parameters

The appropriate print ticket.

## -returns

Returns an HRESULT value. If the property call was not successful, it returns the appropriate HRESULT error code.

Returns **E_ILLEGAL_METHOD_CALL** if called from the the [IPrinterExtensionEvent::OnPrinterQueuesEnumerated](nf-printerextension-iprinterextensionevent-onprinterqueuesenumerated.md) context.

## -see-also


[IPrintSchemaTicket](nn-printerextension-iprintschematicket.md)

[IPrinterExtensionContext](nn-printerextension-iprinterextensioncontext.md)
