---
UID: NN:printerextension.IPrinterPropertyBag
title: IPrinterPropertyBag (printerextension.h)
description: Provides strongly-typed get and set methods.
old-location: print\iprinterpropertybag_interface.htm
tech.root: print
ms.assetid: 421397FF-4956-4052-B63D-32F8E79A22D0
ms.date: 04/20/2018
ms.keywords: IPrinterPropertyBag, IPrinterPropertyBag interface [Print Devices], IPrinterPropertyBag interface [Print Devices],described, print.iprinterpropertybag_interface, printerextension/IPrinterPropertyBag
ms.topic: interface
f1_keywords:
 - "printerextension/IPrinterPropertyBag"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Printerextension.h
api_name:
- IPrinterPropertyBag
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrinterPropertyBag interface


## -description


Provides strongly-typed <b>get</b> and <b>set</b> methods.

Note that the driver property bag uses the following GUID for its property store format ID:

<dl>
<dd>DEFINE_GUID(FMTID_PrinterPropertyBag, 0x75f9adca, 0x097d, 0x45c3, 0xa6, 0xe4, 0xba, 0xb2, 0x9e, 0x27, 0x6f, 0x3e);</dd>
</dl>


The <b>IPrinterPropertyBag</b> interface is used by all the printer property bags, including driver property bag, user property bag, queue property bag, and DEVMODE property bag.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrinterPropertyBag</b> interface inherits from the <a href="ebbff4bc-36b2-4861-9efa-ffa45e013eb5">IDispatch</a> interface. <b>IPrinterPropertyBag</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch">IDispatch</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprinterextensioncontext-get_driverproperties">IPrinterExtensionContext::DriverProperties</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprinterextensioncontext-get_userproperties">IPrinterExtensionContext::UserProperties</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprinterqueue-getproperties">IPrinterQueue::GetProperties</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprinterscriptablepropertybag">IPrinterScriptablePropertyBag</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/print/v4-driver-property-bags">V4 Printer Driver Property Bags</a>
 

 

