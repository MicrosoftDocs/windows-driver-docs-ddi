---
UID: NF:prdrvcom.QueryDeviceNamespace
title: QueryDeviceNamespace function (prdrvcom.h)
description: The IPrintTicketProvider::QueryDeviceNamespace method queries the device for its default namespace uniform resource identifier (URI).
old-location: print\iprintticketprovider_querydevicenamespace.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["QueryDeviceNamespace function"]
ms.keywords: IPrintTicketProvider interface [Print Devices],QueryDeviceNamespace method, IPrintTicketProvider::QueryDeviceNamespace, QueryDeviceNamespace, QueryDeviceNamespace method [Print Devices], QueryDeviceNamespace method [Print Devices],IPrintTicketProvider interface, prdrvcom/IPrintTicketProvider::QueryDeviceNamespace, print.iprintticketprovider_querydevicenamespace, print_ticket-package_af00ca31-6882-4a84-8bc4-c8267b49ce30.xml
f1_keywords:
 - "prdrvcom/IPrintTicketProvider.QueryDeviceNamespace"
 - "IPrintTicketProvider.QueryDeviceNamespace"
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
- IPrintTicketProvider.QueryDeviceNamespace
targetos: Windows
req.typenames: 
---

# QueryDeviceNamespace function


## -description


The <code>IPrintTicketProvider::QueryDeviceNamespace</code> method queries the device for its default namespace uniform resource identifier (URI).


## -parameters




### -param pDefaultNamespace 
[out]
A pointer to a BSTR that receives the namespace URI. The driver places the namespace URI in the buffer that is pointed to by <i>pDefaultNamespace</i>.

<code>IPrintTicketProvider::QueryDeviceNamespace</code> is responsible for allocating the string by means of a call to <b>SysAllocString</b> (described in the Microsoft Windows SDK documentation), but the caller is responsible for freeing the string.


## -returns



<code>IPrintTicketProvider::QueryDeviceNamespace</code> should return S_OK if the operation succeeds and E_FAIL otherwise.



