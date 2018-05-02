---
UID: NF:printerextension.IPrinterScriptablePropertyBag.SetString
title: IPrinterScriptablePropertyBag::SetString
author: windows-driver-content
description: Writes a string property.
old-location: print\iprinterscriptablepropertybag_setstring.htm
old-project: print
ms.assetid: 9B4EBCA4-8370-4F00-9853-6EE8408367BE
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: IPrinterScriptablePropertyBag interface [Print Devices],SetString method, IPrinterScriptablePropertyBag.SetString, IPrinterScriptablePropertyBag::SetString, SetString, SetString method [Print Devices], SetString method [Print Devices],IPrinterScriptablePropertyBag interface, print.iprinterscriptablepropertybag_setstring, printerextension/IPrinterScriptablePropertyBag::SetString
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
-	IPrinterScriptablePropertyBag.SetString
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrinterScriptablePropertyBag::SetString


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



A call to <b>SetString</b> will throw an exception, if the specified property is not found. We recommend that you use a try-catch statement around calls to this method, to allow your app to handle any failures gracefully.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh973217">IPrinterScriptablePropertyBag</a>
 

 

