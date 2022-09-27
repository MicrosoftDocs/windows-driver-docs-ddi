---
UID: NF:prcomoem.IPrintOemPrintTicketProvider.ExpandIntentOptions
title: IPrintOemPrintTicketProvider::ExpandIntentOptions (prcomoem.h)
description: The IPrintOemPrintTicketProvider::ExpandIntentOptions method enables the plug-in to expand printer options (such as photo printing) into individual feature settings in the print ticket.
tech.root: print
ms.date: 08/22/2022
keywords: ["IPrintOemPrintTicketProvider::ExpandIntentOptions"]
ms.keywords: ExpandIntentOptions, ExpandIntentOptions method [Print Devices], ExpandIntentOptions method [Print Devices],IPrintOemPrintTicketProvider interface, IPrintOemPrintTicketProvider interface [Print Devices],ExpandIntentOptions method, IPrintOemPrintTicketProvider.ExpandIntentOptions, IPrintOemPrintTicketProvider::ExpandIntentOptions, prcomoem/IPrintOemPrintTicketProvider::ExpandIntentOptions, print.iprintoemprintticketprovider_expandintentoptions, print_ticket-package_1b344230-a06b-49ca-8b55-eb9c3500c3f1.xml
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
 - IPrintOemPrintTicketProvider::ExpandIntentOptions
 - prcomoem/IPrintOemPrintTicketProvider::ExpandIntentOptions
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - prcomoem.h
api_name:
 - IPrintOemPrintTicketProvider::ExpandIntentOptions
---

## -description

The **IPrintOemPrintTicketProvider::ExpandIntentOptions** method enables the plug-in to expand printer options (such as photo printing) into individual feature settings in the print ticket.

## -parameters

### -param pPrintTicket [in, out]

A pointer to a print ticket.

## -returns

**IPrintOemPrintTicketProvider::ExpandIntentOptions** should return **S_OK** if the operation succeeds or when the plug-in does not support intent features. Otherwise, this method should return a standard COM error code.

## -remarks

The Unidrv or Pscript5 driver calls **IPrintOemPrintTicketProvider::ExpandIntentOptions** to enable the plug-in to expand options that represent intent into their individual settings in other features in the print ticket before print ticket validation. Such option expansion has two important effects: the client receives information about the results of the intent expansion, and the core driver resolves constraints against the individual features that are affected by the intent.

We recommend that the driver preserve the state of the intent option in the driver's private [DEVMODEW](/windows/win32/api/wingdi/ns-wingdi-devmodew) structure when it converts a print ticket to a DEVMODEW, and then from a DEVMODEW back to a print ticket.
