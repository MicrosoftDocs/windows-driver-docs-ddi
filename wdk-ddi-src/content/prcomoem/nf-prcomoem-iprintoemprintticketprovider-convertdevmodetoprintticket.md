---
UID: NF:prcomoem.IPrintOemPrintTicketProvider.ConvertDevModeToPrintTicket
title: IPrintOemPrintTicketProvider::ConvertDevModeToPrintTicket (prcomoem.h)
description: The IPrintOemPrintTicketProvider::ConvertDevModeToPrintTicket method converts a DEVMODEW structure into a print ticket.
tech.root: print
ms.date: 08/22/2022
keywords: ["IPrintOemPrintTicketProvider::ConvertDevModeToPrintTicket"]
ms.keywords: ConvertDevModeToPrintTicket, ConvertDevModeToPrintTicket method [Print Devices], ConvertDevModeToPrintTicket method [Print Devices],IPrintOemPrintTicketProvider interface, IPrintOemPrintTicketProvider interface [Print Devices],ConvertDevModeToPrintTicket method, IPrintOemPrintTicketProvider.ConvertDevModeToPrintTicket, IPrintOemPrintTicketProvider::ConvertDevModeToPrintTicket, prcomoem/IPrintOemPrintTicketProvider::ConvertDevModeToPrintTicket, print.iprintoemprintticketprovider_convertdevmodetoprintticket, print_ticket-package_4605321f-640a-438b-a4cc-6e34ef5521b1.xml
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
 - IPrintOemPrintTicketProvider::ConvertDevModeToPrintTicket
 - prcomoem/IPrintOemPrintTicketProvider::ConvertDevModeToPrintTicket
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - prcomoem.h
api_name:
 - IPrintOemPrintTicketProvider::ConvertDevModeToPrintTicket
---

## -description

The **IPrintOemPrintTicketProvider::ConvertDevModeToPrintTicket** method converts a [DEVMODEW](/windows/win32/api/wingdi/ns-wingdi-devmodew) structure into a print ticket.

## -parameters

### -param cbDevmode [in]

The size, in bytes, of the input [DEVMODEW](/windows/win32/api/wingdi/ns-wingdi-devmodew) structure. The size includes both the public and private portions of this structure.

### -param pDevmode [in]

A pointer to the input DEVMODEW structure.

### -param cbDrvPrivateSize [in]

The size, in bytes, of the plug-in's private DEVMODEW structure.

### -param pPrivateDevmode [in]

A pointer to the plug-in's private [DEVMODEW](/windows/win32/api/wingdi/ns-wingdi-devmodew) structure.

### -param pPrintTicket [in, out]

A pointer to the partially-completed print ticket. When **IPrintOemPrintTicketProvider::ConvertDevModeToPrintTicket** returns, all of the entries in the print ticket should be filled in.

## -returns

**IPrintOemPrintTicketProvider::ConvertDevModeToPrintTicket** should return S_OK if the operation succeeds. Otherwise, this method should return a standard COM error code.

## -remarks

The core driver calls the **IPrintOemPrintTicketProvider::ConvertDevModeToPrintTicket** method with an input print ticket that is populated with public and Unidrv-private or Pscript5-private features. The plug-in is free to set [DEVMODEW](/windows/win32/api/wingdi/ns-wingdi-devmodew) settings in the public part or in the plug-in's private part, based on settings in the input print ticket. In addition to setting new DEVMODEW items, the plug-in can modify existing settings in the public portion of the DEVMODEW structure.

The DEVMODEW structure fields that correlate with the part of the DEVMODEW structure of interest to the client will already have been populated before **IPrintOemPrintTicketProvider::ConvertDevModeToPrintTicket** is called, including the public portion of the DEVMODEW structure and excluding the privately-defined values in the public portion of the DEVMODEW structure.

## -see-also

[IPrintOemPrintTicketProvider](./nn-prcomoem-iprintoemprintticketprovider.md)

[IPrintOemPrintTicketProvider::ConvertPrintTicketToDevMode](./nf-prcomoem-iprintoemprintticketprovider-convertprinttickettodevmode.md)
