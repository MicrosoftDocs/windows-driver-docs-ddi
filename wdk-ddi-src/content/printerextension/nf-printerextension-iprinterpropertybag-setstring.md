---
UID: NF:printerextension.IPrinterPropertyBag.SetString
title: IPrinterPropertyBag::SetString (printerextension.h)
description: Writes a string property.
old-location: print\iprinterpropertybag_setstring.htm
tech.root: print
ms.assetid: FF063DFE-FD80-4E30-8289-5B40642C867F
ms.date: 04/20/2018
ms.keywords: IPrinterPropertyBag interface [Print Devices],SetString method, IPrinterPropertyBag.SetString, IPrinterPropertyBag::SetString, SetString, SetString method [Print Devices], SetString method [Print Devices],IPrinterPropertyBag interface, print.iprinterpropertybag_setstring, printerextension/IPrinterPropertyBag::SetString
ms.topic: method
req.header: printerextension.h
req.include-header: Printerextension.h
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
- Printerextension.h
api_name:
- IPrinterPropertyBag.SetString
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrinterPropertyBag::SetString


## -description


Writes a string property.


## -parameters




### -param bstrName [in]

The property to set.


### -param bstrValue [in]

The property value to set.


## -returns



This method returns an <b>HRESULT</b> value.




## -remarks



In Windows 8.1 a new flag, PRINTER_ACCESS_MANAGE_LIMITED, has been introduced to grant print queue permissions that are more limited than PRINTER_ACCESS_ADMINISTER, but more powerful than 
PRINTER_ACCESS_USE.

The permissions are a subset of those associated with PRINTER_ACCESS_ADMINISTER. This means that if the currently logged-on user has PRINTER_ACCESS_ADMINISTER permission, the user can gain 
PRINTER_ACCESS_MANAGE_LIMITED access to the queue.

A call to set a property on a queue property bag will fail with ERROR_ACCESS_DENIED, if the user does not have the appropriate permission. This behavior was true before PRINTER_ACCESS_MANAGE_LIMITED was introduced, and it's still the current behavior.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nn-printerextension-iprinterpropertybag">IPrinterPropertyBag</a>
 

 

