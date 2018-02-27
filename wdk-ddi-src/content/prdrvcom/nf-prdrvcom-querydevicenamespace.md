---
UID: NF:prdrvcom.QueryDeviceNamespace
title: QueryDeviceNamespace function
author: windows-driver-content
description: The IPrintTicketProvider::QueryDeviceNamespace method queries the device for its default namespace uniform resource identifier (URI).
old-location: print\iprintticketprovider_querydevicenamespace.htm
old-project: print
ms.assetid: d4a36a33-f8b8-4b8c-8ff7-918cb8ba79cb
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IPrintTicketProvider interface [Print Devices], QueryDeviceNamespace method, IPrintTicketProvider::QueryDeviceNamespace, QueryDeviceNamespace, QueryDeviceNamespace method [Print Devices], QueryDeviceNamespace method [Print Devices], IPrintTicketProvider interface, prdrvcom/IPrintTicketProvider::QueryDeviceNamespace, print.iprintticketprovider_querydevicenamespace, print_ticket-package_af00ca31-6882-4a84-8bc4-c8267b49ce30.xml
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
-	IPrintTicketProvider.QueryDeviceNamespace
product: Windows
targetos: Windows
req.typenames: SHIMOPTS, *PSHIMOPTS
req.product: Windows 10 or later.
---

# QueryDeviceNamespace function


## -description


The <code>IPrintTicketProvider::QueryDeviceNamespace</code> method queries the device for its default namespace uniform resource identifier (URI).


## -syntax


````
HRESULT QueryDeviceNamespace(
  [out] BSTR *pDefaultNamespace
);
````


## -parameters




### -param pDefaultNamespace [out]

A pointer to a BSTR that receives the namespace URI. The driver places the namespace URI in the buffer that is pointed to by <i>pDefaultNamespace</i>.

<code>IPrintTicketProvider::QueryDeviceNamespace</code> is responsible for allocating the string by means of a call to <b>SysAllocString</b> (described in the Microsoft Windows SDK documentation), but the caller is responsible for freeing the string.


## -returns



<code>IPrintTicketProvider::QueryDeviceNamespace</code> should return S_OK if the operation succeeds and E_FAIL otherwise.



