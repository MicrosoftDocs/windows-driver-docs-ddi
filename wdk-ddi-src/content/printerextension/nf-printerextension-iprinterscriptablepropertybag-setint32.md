---
UID: NF:printerextension.IPrinterScriptablePropertyBag.SetInt32
title: IPrinterScriptablePropertyBag::SetInt32
description: Writes an integer property.
old-location: print\iprinterscriptablepropertybag_setint32.htm
tech.root: print
ms.assetid: 40A057F7-AC9B-4F16-8FE2-490CEECAB523
ms.date: 04/20/2018
ms.keywords: IPrinterScriptablePropertyBag interface [Print Devices],SetInt32 method, IPrinterScriptablePropertyBag.SetInt32, IPrinterScriptablePropertyBag::SetInt32, SetInt32, SetInt32 method [Print Devices], SetInt32 method [Print Devices],IPrinterScriptablePropertyBag interface, print.iprinterscriptablepropertybag_setint32, printerextension/IPrinterScriptablePropertyBag::SetInt32
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
-	IPrinterScriptablePropertyBag.SetInt32
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrinterScriptablePropertyBag::SetInt32


## -description


Writes an integer property.


## -parameters




### -param bstrName [in]

The property to set.


### -param nValue [in]

The new value to set.


## -returns



This method returns an <b>HRESULT</b> value.




## -remarks



A call to <b>SetInt32</b> will throw an exception, if the specified property is not found. We recommend that you use a try-catch statement around calls to this method, to allow your app to handle any failures gracefully.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh973217">IPrinterScriptablePropertyBag</a>
 

 

