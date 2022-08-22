---
UID: NF:prdrvcom.GetPrintCapabilities
title: GetPrintCapabilities function (prdrvcom.h)
description: The IPrintOemPrintTicketProvider::GetPrintCapabilities method queries the provider for a complete print capabilities document that describes the printer's features and parameters.
tech.root: print
ms.date: 08/22/2022
keywords: ["GetPrintCapabilities function"]
ms.keywords: GetPrintCapabilities, GetPrintCapabilities method [Print Devices], GetPrintCapabilities method [Print Devices],IPrintOemPrintTicketProvider interface, IPrintOemPrintTicketProvider interface [Print Devices],GetPrintCapabilities method, IPrintOemPrintTicketProvider::GetPrintCapabilities, prdrvcom/IPrintOemPrintTicketProvider::GetPrintCapabilities, print.IPrintOemPrintTicketProvider_getprintcapabilities, print_ticket-package_82407167-f510-4a1d-acd4-1baaac8e1928.xml
f1_keywords:
 - "prdrvcom/IPrintOemPrintTicketProvider.GetPrintCapabilities"
 - "IPrintOemPrintTicketProvider.GetPrintCapabilities"
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- prdrvcom.h
api_name:
- IPrintOemPrintTicketProvider.GetPrintCapabilities
targetos: Windows
req.typenames: 
---

## -description

The **IPrintOemPrintTicketProvider::GetPrintCapabilities** method queries the provider for a complete print capabilities document that describes the printer's features and parameters.

## -parameters

### -param pPrintTicket [in]

A pointer to the print ticket. The settings of the print ticket constrain the device capabilities.

### -param ppCapabilities [out]

A pointer to a variable that receives the address of the device capabilities document.

## -returns

**IPrintOemPrintTicketProvider::GetPrintCapabilities** should return S_OK if the operation succeeds. Otherwise, this method should return a standard COM error code.

## -remarks

The input print ticket should be used to determine and describe constraints on the settings in the output print capabilities document. No features, options, and parameters that are described in the output print capabilities document should change because of the contents of the input print ticket. Only the constraint status of the features, options, and parameters are subject to change.
