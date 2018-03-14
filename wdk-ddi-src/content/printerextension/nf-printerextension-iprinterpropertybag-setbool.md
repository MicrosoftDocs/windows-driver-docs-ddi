---
UID: NF:printerextension.IPrinterPropertyBag.SetBool
title: IPrinterPropertyBag::SetBool method
author: windows-driver-content
description: Writes a specified boolean property value.
old-location: print\iprinterpropertybag_setbool.htm
old-project: print
ms.assetid: B97C3FE9-0AC8-4147-A394-3344EBBA0B4C
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrinterPropertyBag, IPrinterPropertyBag interface [Print Devices], SetBool method, IPrinterPropertyBag::SetBool, SetBool method [Print Devices], SetBool method [Print Devices], IPrinterPropertyBag interface, SetBool,IPrinterPropertyBag.SetBool, print.iprinterpropertybag_setbool, printerextension/IPrinterPropertyBag::SetBool
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Printerextension.h
api_name:
-	IPrinterPropertyBag.SetBool
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrinterPropertyBag::SetBool method


## -description


Writes a specified boolean property value.


## -syntax


````
HRESULT SetBool(
  [in] BSTR bstrName,
  [in] BOOL bValue
);
````


## -parameters




### -param bstrName [in]

The property to set.


### -param bValue [in]

The value to set.


## -returns



This method returns an <b>HRESULT</b> value.




## -remarks



In Windows 8.1 a new flag, PRINTER_ACCESS_MANAGE_LIMITED, has been introduced to grant print queue permissions that are more limited than PRINTER_ACCESS_ADMINISTER, but more powerful than 
PRINTER_ACCESS_USE.

The permissions are a subset of those associated with PRINTER_ACCESS_ADMINISTER. This means that if the currently logged-on user has PRINTER_ACCESS_ADMINISTER permission, the user can gain 
PRINTER_ACCESS_MANAGE_LIMITED access to the queue.

A call to set a property on a queue property bag will fail with ERROR_ACCESS_DENIED, if the user does not have the appropriate permission. This behavior was true before PRINTER_ACCESS_MANAGE_LIMITED was introduced, and it's still the current behavior.




## -see-also

<a href="..\printerextension\nn-printerextension-iprinterpropertybag.md">IPrinterPropertyBag</a>



 

 


