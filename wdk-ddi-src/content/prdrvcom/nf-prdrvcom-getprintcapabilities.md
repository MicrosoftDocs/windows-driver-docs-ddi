---
UID: NF:prdrvcom.GetPrintCapabilities
title: GetPrintCapabilities function
author: windows-driver-content
description: The IPrintTicketProvider::GetPrintCapabilities method queries the provider for a complete print capabilities document that describes the printer's features and parameters.
old-location: print\iprintticketprovider_getprintcapabilities.htm
old-project: print
ms.assetid: 12dfd953-2336-47ce-8fdc-df8c6138b31d
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: GetPrintCapabilities, GetPrintCapabilities method [Print Devices], GetPrintCapabilities method [Print Devices], IPrintTicketProvider interface, IPrintTicketProvider interface [Print Devices], GetPrintCapabilities method, IPrintTicketProvider::GetPrintCapabilities, prdrvcom/IPrintTicketProvider::GetPrintCapabilities, print.iprintticketprovider_getprintcapabilities, print_ticket-package_82407167-f510-4a1d-acd4-1baaac8e1928.xml
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
-	IPrintTicketProvider.GetPrintCapabilities
product: Windows
targetos: Windows
req.typenames: SHIMOPTS, *PSHIMOPTS
req.product: Windows 10 or later.
---

# GetPrintCapabilities function


## -description


The <code>IPrintTicketProvider::GetPrintCapabilities</code> method queries the provider for a complete print capabilities document that describes the printer's features and parameters.


## -syntax


````
HRESULT GetPrintCapabilities(
  [in]  IXMLDOMDocument2 *pPrintTicket,
  [out] IXMLDOMDocument2 **ppCapabilities
);
````


## -parameters




### -param pPrintTicket [in]

A pointer to the print ticket. The settings of the print ticket constrain the device capabilities.


### -param ppCapabilities [out]

A pointer to a variable that receives the address of the device capabilities document. 


## -returns



<code>IPrintTicketProvider::GetPrintCapabilities</code> should return S_OK if the operation succeeds. Otherwise, this method should return a standard COM error code.




## -remarks



The input print ticket should be used to determine and describe constraints on the settings in the output print capabilities document. No features, options, and parameters that are described in the output print capabilities document should change because of the contents of the input print ticket. Only the constraint status of the features, options, and parameters are subject to change.



