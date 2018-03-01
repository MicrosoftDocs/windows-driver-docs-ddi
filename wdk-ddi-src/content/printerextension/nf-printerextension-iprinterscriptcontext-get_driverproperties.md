---
UID: NF:printerextension.IPrinterScriptContext.get_DriverProperties
title: IPrinterScriptContext::get_DriverProperties method
author: windows-driver-content
description: Gets the driver property bag.
old-location: print\iprinterextensioncontext_driverproperties.htm
old-project: print
ms.assetid: 52EC01D5-43C7-4CE0-ABEC-1604A4198316
ms.author: windowsdriverdev
ms.date: 2/23/2018
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
req.lib: printerextension.h
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

<a href="..\printerextension\nn-printerextension-iprinterpropertybag.md">IPrinterPropertyBag</a>



<a href="..\printerextension\nn-printerextension-iprinterextensioncontext.md">IPrinterExtensionContext</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterExtensionContext::DriverProperties property%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

