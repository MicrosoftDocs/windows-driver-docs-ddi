---
UID: NF:printerextension.IPrinterScriptContext.get_DriverProperties
title: IPrinterScriptContext::get_DriverProperties method
author: windows-driver-content
description: Gets the driver property bag.
old-location: print\iprinterextensioncontext_driverproperties.htm
old-project: print
ms.assetid: 52EC01D5-43C7-4CE0-ABEC-1604A4198316
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DriverProperties property [Print Devices], DriverProperties property [Print Devices], IPrinterExtensionContext interface, IPrinterExtensionContext interface [Print Devices], DriverProperties property, IPrinterExtensionContext.DriverProperties, IPrinterExtensionContext::get_DriverProperties, IPrinterScriptContext, IPrinterScriptContext::get_DriverProperties, get_DriverProperties, get_DriverProperties,IPrinterScriptContext.get_DriverProperties, print.iprinterextensioncontext_driverproperties, printerextension/IPrinterExtensionContext::DriverProperties, printerextension/IPrinterExtensionContext::get_DriverProperties
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
-	IPrinterExtensionContext.DriverProperties
-	IPrinterExtensionContext.get_DriverProperties
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrinterScriptContext::get_DriverProperties method


## -description


Gets the driver property bag.

This property is read-only.


## -syntax


````
HRESULT get_DriverProperties(
  [out, retval] IPrinterPropertyBag **ppPropertyBag
);
````


## -parameters


## -remarks



The driver property bag uses the following GUID for its property store format ID:

<code>DEFINE_GUID(FMTID_PrinterPropertyBag, 0x75f9adca, 0x097d, 0x45c3, 0xa6, 0xe4, 0xba, 0xb2, 0x9e, 0x27, 0x6f, 0x3e);</code>




## -see-also

<a href="..\printerextension\nn-printerextension-iprinterextensioncontext.md">IPrinterExtensionContext</a>



<a href="..\printerextension\nn-printerextension-iprinterpropertybag.md">IPrinterPropertyBag</a>



 

 


