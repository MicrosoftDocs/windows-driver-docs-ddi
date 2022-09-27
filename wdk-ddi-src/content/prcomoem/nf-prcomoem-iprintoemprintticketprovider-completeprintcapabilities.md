---
UID: NF:prcomoem.IPrintOemPrintTicketProvider.CompletePrintCapabilities
title: IPrintOemPrintTicketProvider::CompletePrintCapabilities (prcomoem.h)
description: The IPrintOemPrintTicketProvider::CompletePrintCapabilities method fills in the remaining entries of the specified print capabilities document.
tech.root: print
ms.date: 08/22/2022
keywords: ["IPrintOemPrintTicketProvider::CompletePrintCapabilities"]
ms.keywords: CompletePrintCapabilities, CompletePrintCapabilities method [Print Devices], CompletePrintCapabilities method [Print Devices],IPrintOemPrintTicketProvider interface, IPrintOemPrintTicketProvider interface [Print Devices],CompletePrintCapabilities method, IPrintOemPrintTicketProvider.CompletePrintCapabilities, IPrintOemPrintTicketProvider::CompletePrintCapabilities, prcomoem/IPrintOemPrintTicketProvider::CompletePrintCapabilities, print.iprintoemprintticketprovider_completeprintcapabilities, print_ticket-package_75d63289-6e10-4731-a2b1-16f396f21d62.xml
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
 - IPrintOemPrintTicketProvider::CompletePrintCapabilities
 - prcomoem/IPrintOemPrintTicketProvider::CompletePrintCapabilities
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - prcomoem.h
api_name:
 - IPrintOemPrintTicketProvider::CompletePrintCapabilities
---

## -description

The **IPrintOemPrintTicketProvider::CompletePrintCapabilities** method fills in the remaining entries of the specified print capabilities document.

## -parameters

### -param pPrintTicket [in]

A pointer to an input print ticket. Any configuration-dependent data in the print capabilities (that is, data that would be represented by a **Switch** / **Case** construct in a GPD file) must be based on the settings in the print ticket. If the application does not provide a print ticket, this parameter can be **NULL**. In such situations, the provider should assume default settings for feature and parameter constructs.

### -param pCapabilities [in, out]

A pointer to a partially-complete print capabilities document. When **IPrintOemPrintTicketProvider::CompletePrintCapabilities** returns, the buffer that is pointed to by *pCapablities* should contain a completed print capabilities document.

## -returns

**IPrintOemPrintTicketProvider::CompletePrintCapabilities** should return **S_OK** if the operation succeeds. Otherwise, this method should return a standard COM error code.

## -remarks

A Unidrv or Pscript5 plug-in should fill in only those capabilities that it explicitly supports, over and above the features and options that the driver supports. The plug-in should at least fill in the capabilities that it supports, as listed in its private DEVMODEW structure. If the plug-in provider changes the representation of features provided by the core driver in the print ticket, the provider must make equivalent changes to the representation here.
