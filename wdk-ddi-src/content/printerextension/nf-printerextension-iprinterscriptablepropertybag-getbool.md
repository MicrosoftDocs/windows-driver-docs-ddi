---
UID: NF:printerextension.IPrinterScriptablePropertyBag.GetBool
title: IPrinterScriptablePropertyBag::GetBool method
author: windows-driver-content
description: Gets a specified boolean property.
old-location: print\iprinterscriptablepropertybag_getbool.htm
old-project: print
ms.assetid: EEBB916B-0E7B-4523-BB13-A4758F5491BB
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetBool method [Print Devices], GetBool method [Print Devices], IPrinterScriptablePropertyBag interface, GetBool,IPrinterScriptablePropertyBag.GetBool, IPrinterScriptablePropertyBag, IPrinterScriptablePropertyBag interface [Print Devices], GetBool method, IPrinterScriptablePropertyBag::GetBool, print.iprinterscriptablepropertybag_getbool, printerextension/IPrinterScriptablePropertyBag::GetBool
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Printerextension.h
api_name:
-	IPrinterScriptablePropertyBag.GetBool
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrinterScriptablePropertyBag::GetBool method


## -description


Gets a specified boolean property.


## -syntax


````
HRESULT GetBool(
  [in]          BSTR bstrName,
  [out, retval] BOOL *pbValue
);
````


## -parameters




### -param bstrName [in]

The name of the property.


### -param pbValue [out, retval]

The returned property value.


## -returns



This method returns an <b>HRESULT</b> value.




## -remarks



A call to <b>GetBool</b> will throw an exception, if the specified property is not found. We recommend that you use a try-catch statement around calls to this method, to allow your app to handle any failures gracefully.




## -see-also

<a href="..\printerextension\nn-printerextension-iprinterscriptablepropertybag.md">IPrinterScriptablePropertyBag</a>



 

 


