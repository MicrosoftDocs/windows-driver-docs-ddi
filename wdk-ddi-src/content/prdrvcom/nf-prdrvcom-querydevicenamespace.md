---
UID: NF:prdrvcom.QueryDeviceNamespace
title: QueryDeviceNamespace function (prdrvcom.h)
description: The IPrintOemPrintTicketProvider::QueryDeviceNamespace method queries the device for its default namespace uniform resource identifier (URI).
tech.root: print
ms.date: 08/22/2022
keywords: ["QueryDeviceNamespace function"]
ms.keywords: IPrintOemPrintTicketProvider interface [Print Devices],QueryDeviceNamespace method, IPrintOemPrintTicketProvider::QueryDeviceNamespace, QueryDeviceNamespace, QueryDeviceNamespace method [Print Devices], QueryDeviceNamespace method [Print Devices],IPrintOemPrintTicketProvider interface, prdrvcom/IPrintOemPrintTicketProvider::QueryDeviceNamespace, print.IPrintOemPrintTicketProvider_querydevicenamespace, print_ticket-package_af00ca31-6882-4a84-8bc4-c8267b49ce30.xml
f1_keywords:
 - "prdrvcom/IPrintOemPrintTicketProvider.QueryDeviceNamespace"
 - "IPrintOemPrintTicketProvider.QueryDeviceNamespace"
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
- IPrintOemPrintTicketProvider.QueryDeviceNamespace
targetos: Windows
req.typenames: 
---

## -description

The **IPrintOemPrintTicketProvider::QueryDeviceNamespace** method queries the device for its default namespace uniform resource identifier (URI).

## -parameters

### -param pDefaultNamespace [out]

A pointer to a BSTR that receives the namespace URI. The driver places the namespace URI in the buffer that is pointed to by *pDefaultNamespace*.

**IPrintOemPrintTicketProvider::QueryDeviceNamespace** is responsible for allocating the string by means of a call to **SysAllocString** (described in the Microsoft Windows SDK documentation), but the caller is responsible for freeing the string.

## -returns

**IPrintOemPrintTicketProvider::QueryDeviceNamespace** should return S_OK if the operation succeeds and E_FAIL otherwise.
