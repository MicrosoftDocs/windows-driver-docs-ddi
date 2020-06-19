---
UID: NF:prcomoem.IPrintOemPrintTicketProvider.ConvertDevModeToPrintTicket
title: IPrintOemPrintTicketProvider::ConvertDevModeToPrintTicket (prcomoem.h)
description: The IPrintOemPrintTicketProvider::ConvertDevModeToPrintTicket method converts a DEVMODEW structure into a print ticket.
old-location: print\iprintoemprintticketprovider_convertdevmodetoprintticket.htm
tech.root: print
ms.assetid: b2e029b7-32c0-4cef-8388-9d30aa5610d3
ms.date: 04/20/2018
keywords: ["IPrintOemPrintTicketProvider::ConvertDevModeToPrintTicket"]
ms.keywords: ConvertDevModeToPrintTicket, ConvertDevModeToPrintTicket method [Print Devices], ConvertDevModeToPrintTicket method [Print Devices],IPrintOemPrintTicketProvider interface, IPrintOemPrintTicketProvider interface [Print Devices],ConvertDevModeToPrintTicket method, IPrintOemPrintTicketProvider.ConvertDevModeToPrintTicket, IPrintOemPrintTicketProvider::ConvertDevModeToPrintTicket, prcomoem/IPrintOemPrintTicketProvider::ConvertDevModeToPrintTicket, print.iprintoemprintticketprovider_convertdevmodetoprintticket, print_ticket-package_4605321f-640a-438b-a4cc-6e34ef5521b1.xml
f1_keywords:
 - "prcomoem/IPrintOemPrintTicketProvider.ConvertDevModeToPrintTicket"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- prcomoem.h
api_name:
- IPrintOemPrintTicketProvider.ConvertDevModeToPrintTicket
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemPrintTicketProvider::ConvertDevModeToPrintTicket


## -description


The <code>IPrintOemPrintTicketProvider::ConvertDevModeToPrintTicket</code> method converts a <a href="https://docs.microsoft.com/windows/win32/api/wingdi/ns-wingdi-devicemodew">DEVMODEW</a> structure into a print ticket. 


## -parameters




### -param cbDevmode [in]

The size, in bytes, of the input <a href="https://docs.microsoft.com/windows/win32/api/wingdi/ns-wingdi-devicemodew">DEVMODEW</a> structure. The size includes both the public and private portions of this structure.


### -param pDevmode [in]

A pointer to the input DEVMODEW structure.


### -param cbDrvPrivateSize [in]

The size, in bytes, of the plug-in's private DEVMODEW structure. 


### -param pPrivateDevmode [in]

A pointer to the plug-in's private <a href="https://docs.microsoft.com/windows/win32/api/wingdi/ns-wingdi-devicemodew">DEVMODEW</a> structure.


### -param pPrintTicket [in, out]

A pointer to the partially-completed print ticket. When <code>IPrintOemPrintTicketProvider::ConvertDevModeToPrintTicket</code> returns, all of the entries in the print ticket should be filled in.


## -returns



<code>IPrintOemPrintTicketProvider::ConvertDevModeToPrintTicket</code> should return S_OK if the operation succeeds. Otherwise, this method should return a standard COM error code.




## -remarks



The core driver calls the <code>IPrintTicketProvider::ConvertDevModeToPrintTicket</code> method with an input print ticket that is populated with public and Unidrv-private or Pscript5-private features. The plug-in is free to set <a href="https://docs.microsoft.com/windows/win32/api/wingdi/ns-wingdi-devicemodew">DEVMODEW</a> settings in the public part or in the plug-in's private part, based on settings in the input print ticket. In addition to setting new DEVMODEW items, the plug-in can modify existing settings in the public portion of the DEVMODEW structure.

The DEVMODEW structure fields that correlate with the part of the DEVMODEW structure of interest to the client will already have been populated before <code>IPrintOemPrintTicketProvider::ConvertDevModeToPrintTicket</code> is called, including the public portion of the DEVMODEW structure and excluding the privately-defined values in the public portion of the DEVMODEW structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nn-prcomoem-iprintoemprintticketprovider">IPrintOemPrintTicketProvider</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemprintticketprovider-convertprinttickettodevmode">IPrintOemPrintTicketProvider::ConvertPrintTicketToDevMode</a>
 

 


