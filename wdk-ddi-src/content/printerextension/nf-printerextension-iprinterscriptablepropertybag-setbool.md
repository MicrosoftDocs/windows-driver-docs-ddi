---
UID: NF:printerextension.IPrinterScriptablePropertyBag.SetBool
title: IPrinterScriptablePropertyBag::SetBool
description: Writes a specified boolean property value.
old-location: print\iprinterscriptablepropertybag_setbool.htm
tech.root: print
ms.assetid: 8970833A-7CBA-40EB-85A8-60E7730C052F
ms.date: 04/20/2018
ms.keywords: IPrinterScriptablePropertyBag interface [Print Devices],SetBool method, IPrinterScriptablePropertyBag.SetBool, IPrinterScriptablePropertyBag::SetBool, SetBool, SetBool method [Print Devices], SetBool method [Print Devices],IPrinterScriptablePropertyBag interface, print.iprinterscriptablepropertybag_setbool, printerextension/IPrinterScriptablePropertyBag::SetBool
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
-	IPrinterScriptablePropertyBag.SetBool
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrinterScriptablePropertyBag::SetBool


## -description


Writes a specified boolean property value.


## -parameters




### -param bstrName [in]

The property to set.


### -param bValue [in]

The value to set.


## -returns



This method returns an <b>HRESULT</b> value.




## -remarks



A call to <b>SetBool</b> will throw an exception, if the specified property is not found. We recommend that you use a try-catch statement around calls to this method, to allow your app to handle any failures gracefully.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh973217">IPrinterScriptablePropertyBag</a>
 

 

