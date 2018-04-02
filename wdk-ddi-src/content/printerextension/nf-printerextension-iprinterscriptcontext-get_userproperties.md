---
UID: NF:printerextension.IPrinterScriptContext.get_UserProperties
title: IPrinterScriptContext::get_UserProperties method
author: windows-driver-content
description: Provides access to the user property bag, if the property bag is present.
old-location: print\iprinterscriptcontext_userproperties.htm
old-project: print
ms.assetid: 6F181350-41A3-4592-BB72-1E3AD6FEC748
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrinterScriptContext, IPrinterScriptContext interface [Print Devices], UserProperties property, IPrinterScriptContext.UserProperties, IPrinterScriptContext::get_UserProperties, UserProperties property [Print Devices], UserProperties property [Print Devices], IPrinterScriptContext interface, get_UserProperties, get_UserProperties,IPrinterScriptContext.get_UserProperties, print.iprinterscriptcontext_userproperties, printerextension/IPrinterScriptContext::UserProperties, printerextension/IPrinterScriptContext::get_UserProperties
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
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
-	IPrinterScriptContext.UserProperties
-	IPrinterScriptContext.get_UserProperties
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrinterScriptContext::get_UserProperties method


## -description


Provides access to the user property bag, if the property bag is present.

This property is read-only.


## -parameters


## -remarks



The user property bag is not available in (constraint) JavaScript functions when the functions are called during de-spooling. Therefore JavaScript functions should be designed to handle the situation when there is  a failure to retrieve the user property bag.

<div class="alert"><b>Note</b>  Although the <b>UserProperties</b> property is read-only, the user property bag is a read/write property bag.</div>
<div> </div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh768279">IPrinterScriptContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh973217">IPrinterScriptablePropertyBag</a>
 

 

