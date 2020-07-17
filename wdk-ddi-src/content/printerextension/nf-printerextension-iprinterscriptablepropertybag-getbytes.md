---
UID: NF:printerextension.IPrinterScriptablePropertyBag.GetBytes
title: IPrinterScriptablePropertyBag::GetBytes (printerextension.h)
description: Gets a byte array property.
old-location: print\iprinterscriptablepropertybag_getbytes.htm
tech.root: print
ms.assetid: 419BCBB6-634A-421D-A940-8690BCCF1AC6
ms.date: 04/20/2018
keywords: ["IPrinterScriptablePropertyBag::GetBytes"]
ms.keywords: GetBytes, GetBytes method [Print Devices], GetBytes method [Print Devices],IPrinterScriptablePropertyBag interface, IPrinterScriptablePropertyBag interface [Print Devices],GetBytes method, IPrinterScriptablePropertyBag.GetBytes, IPrinterScriptablePropertyBag::GetBytes, print.iprinterscriptablepropertybag_getbytes, printerextension/IPrinterScriptablePropertyBag::GetBytes
f1_keywords:
 - "printerextension/IPrinterScriptablePropertyBag.GetBytes"
 - "IPrinterScriptablePropertyBag.GetBytes"
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
- Printerextension.h
api_name:
- IPrinterScriptablePropertyBag.GetBytes
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrinterScriptablePropertyBag::GetBytes


## -description


Gets a byte array property.


## -parameters




### -param bstrName [in]

The property to read.


### -param ppArray






#### - ppdispArray [out, retval]

The returned JavaScript array.


## -returns



This method returns an <b>HRESULT</b> value.




## -remarks



A call to <b>GetBytes</b> will throw an exception, if the specified property is not found. We recommend that you use a try-catch statement around calls to this method, to allow your app to handle any failures gracefully.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprinterscriptablepropertybag">IPrinterScriptablePropertyBag</a>
 

 

