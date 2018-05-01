---
UID: NF:printerextension.IPrinterScriptablePropertyBag.SetBytes
title: IPrinterScriptablePropertyBag::SetBytes
author: windows-driver-content
description: Writes a byte array property.
old-location: print\iprinterscriptablepropertybag_setbytes.htm
old-project: print
ms.assetid: 517CF135-A5D7-4C99-8592-59934E24DEE3
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: IPrinterScriptablePropertyBag interface [Print Devices],SetBytes method, IPrinterScriptablePropertyBag.SetBytes, IPrinterScriptablePropertyBag::SetBytes, SetBytes, SetBytes method [Print Devices], SetBytes method [Print Devices],IPrinterScriptablePropertyBag interface, print.iprinterscriptablepropertybag_setbytes, printerextension/IPrinterScriptablePropertyBag::SetBytes
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
-	IPrinterScriptablePropertyBag.SetBytes
product: Windows
targetos: Windows
req.typenames: 
---

# IPrinterScriptablePropertyBag::SetBytes


## -description


Writes a byte array property.


## -parameters




### -param bstrName [in]

The array to write to.


### -param pArray






#### - pdispArray [in]

The JavaScript array to write.


## -returns



This method returns an <b>HRESULT</b> value.




## -remarks



A call to <b>SetBytes</b> will throw an exception, if the specified property is not found. We recommend that you use a try-catch statement around calls to this method, to allow your app to handle any failures gracefully.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh973217">IPrinterScriptablePropertyBag</a>
 

 

