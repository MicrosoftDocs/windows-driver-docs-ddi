---
UID: NF:printerextension.IPrinterScriptContext.get_QueueProperties
title: IPrinterScriptContext::get_QueueProperties method
author: windows-driver-content
description: Provides access to the queue property bag, if the property bag is present.
old-location: print\iprinterscriptcontext_queueproperties.htm
old-project: print
ms.assetid: EEC61313-5796-42BC-84BF-CF29F8BE0C96
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrinterScriptContext, IPrinterScriptContext interface [Print Devices], QueueProperties property, IPrinterScriptContext.QueueProperties, IPrinterScriptContext::get_QueueProperties, QueueProperties property [Print Devices], QueueProperties property [Print Devices], IPrinterScriptContext interface, get_QueueProperties, get_QueueProperties,IPrinterScriptContext.get_QueueProperties, print.iprinterscriptcontext_queueproperties, printerextension/IPrinterScriptContext::QueueProperties, printerextension/IPrinterScriptContext::get_QueueProperties
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
-	IPrinterScriptContext.QueueProperties
-	IPrinterScriptContext.get_QueueProperties
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrinterScriptContext::get_QueueProperties method


## -description


Provides access to the queue property bag, if the property bag is present.

This property is read-only.


## -syntax


````
HRESULT get_QueueProperties(
  [out, retval] IPrinterScriptablePropertyBag **ppPropertyBag
);
````


## -parameters


## -see-also

<a href="..\printerextension\nn-printerextension-iprinterscriptablepropertybag.md">IPrinterScriptablePropertyBag</a>



<a href="..\printerextension\nn-printerextension-iprinterscriptcontext.md">IPrinterScriptContext</a>



 

 


