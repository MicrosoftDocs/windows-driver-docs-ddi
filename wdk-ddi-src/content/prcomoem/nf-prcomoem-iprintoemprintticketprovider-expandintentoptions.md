---
UID: NF:prcomoem.IPrintOemPrintTicketProvider.ExpandIntentOptions
title: IPrintOemPrintTicketProvider::ExpandIntentOptions method
author: windows-driver-content
description: The IPrintOemPrintTicketProvider::ExpandIntentOptions method enables the plug-in to expand printer options (such as photo printing) into individual feature settings in the print ticket.
old-location: print\iprintoemprintticketprovider_expandintentoptions.htm
old-project: print
ms.assetid: c0499a9b-8f02-4a88-bffa-e088e9098a6c
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , ,, ., :, E, ExpandIntentOptions, ExpandIntentOptions method [Print Devices], ExpandIntentOptions method [Print Devices], IPrintOemPrintTicketProvider interface, ExpandIntentOptions,IPrintOemPrintTicketProvider.ExpandIntentOptions, I, IPrintOemPrintTicketProvider, IPrintOemPrintTicketProvider interface [Print Devices], ExpandIntentOptions method, IPrintOemPrintTicketProvider::ExpandIntentOptions, O, P, T, a, c, d, e, i, k, m, n, o, p, prcomoem/IPrintOemPrintTicketProvider::ExpandIntentOptions, print.iprintoemprintticketprovider_expandintentoptions, print_ticket-package_1b344230-a06b-49ca-8b55-eb9c3500c3f1.xml, r, s, t, v, x"
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
req.lib: prcomoem.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	prcomoem.h
apiname:
-	IPrintOemPrintTicketProvider.ExpandIntentOptions
product: Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintOemPrintTicketProvider::ExpandIntentOptions method


## -description


The <code>IPrintOemPrintTicketProvider::ExpandIntentOptions</code> method enables the plug-in to expand printer options (such as photo printing) into individual feature settings in the print ticket. 


## -syntax


````
HRESULT ExpandIntentOptions(
  [in, out] IXMLDOMDocument2 *pPrintTicket
);
````


## -parameters




### -param pPrintTicket [in, out]

A pointer to a print ticket.


## -returns



<code>IPrintOemPrintTicketProvider::ExpandIntentOptions</code> should return S_OK if the operation succeeds or when the plug-in does not support intent features. Otherwise, this method should return a standard COM error code.




## -remarks



The Unidrv or Pscript5 driver calls <code>IPrintOemPrintTicketProvider::ExpandIntentOptions</code> to enable the plug-in to expand options that represent intent into their individual settings in other features in the print ticket before print ticket validation. Such option expansion has two important effects: the client receives information about the results of the intent expansion, and the core driver resolves constraints against the individual features that are affected by the intent.

We recommend that the driver preserve the state of the intent option in the driver's private <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure when it converts a print ticket to a DEVMODEW, and then from a DEVMODEW back to a print ticket.



