---
UID: NF:printerextension.IPrinterScriptablePropertyBag.GetBool
title: IPrinterScriptablePropertyBag::GetBool
author: windows-driver-content
description: Gets a specified boolean property.
old-location: print\iprinterscriptablepropertybag_getbool.htm
tech.root: print
ms.assetid: EEBB916B-0E7B-4523-BB13-A4758F5491BB
ms.date: 04/20/2018
ms.keywords: GetBool, GetBool method [Print Devices], GetBool method [Print Devices],IPrinterScriptablePropertyBag interface, IPrinterScriptablePropertyBag interface [Print Devices],GetBool method, IPrinterScriptablePropertyBag.GetBool, IPrinterScriptablePropertyBag::GetBool, print.iprinterscriptablepropertybag_getbool, printerextension/IPrinterScriptablePropertyBag::GetBool
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrinterScriptablePropertyBag::GetBool


## -description


Gets a specified boolean property.


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




<a href="https://msdn.microsoft.com/library/windows/hardware/hh973217">IPrinterScriptablePropertyBag</a>
 

 

