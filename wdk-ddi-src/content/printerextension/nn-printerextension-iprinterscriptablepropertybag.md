---
UID: NN:printerextension.IPrinterScriptablePropertyBag
title: IPrinterScriptablePropertyBag (printerextension.h)
description: The IPrinterScriptablePropertyBag interface is the property bag interface passed to script clients.
old-location: print\iprinterscriptablepropertybag.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["IPrinterScriptablePropertyBag interface"]
ms.keywords: IPrinterScriptablePropertyBag, IPrinterScriptablePropertyBag interface [Print Devices], IPrinterScriptablePropertyBag interface [Print Devices],described, print.iprinterscriptablepropertybag, printerextension/IPrinterScriptablePropertyBag
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IPrinterScriptablePropertyBag
 - printerextension/IPrinterScriptablePropertyBag
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrinterScriptablePropertyBag
---

# IPrinterScriptablePropertyBag interface


## -description

The IPrinterScriptablePropertyBag interface is the property bag interface passed to script clients. 

This interface is the same as <a href="/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprinterpropertybag">IPrinterPropertyBag</a>, except that the GetBytes and SetBytes methods operate on JavaScript arrays and the GetReadStream and GetWriteStream methods operate on <a href="/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprinterscriptablestream">IPrinterScriptableStream</a> objects.

## -inheritance

The <b xmlns:loc="https://microsoft.com/wdcml/l10n">IPrinterScriptablePropertyBag</b> interface inherits from the <a href="/windows/win32/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IPrinterScriptablePropertyBag</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -see-also

<a href="/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprinterpropertybag">IPrinterPropertyBag</a>



<a href="/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprinterscriptcontext-get_driverproperties">IPrinterScriptContext::DriverProperties</a>



<a href="/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprinterscriptcontext-get_queueproperties">IPrinterScriptContext::QueueProperties</a>



<a href="/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprinterscriptcontext-get_userproperties">IPrinterScriptContext::UserProperties</a>



<a href="/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprinterscriptablestream">IPrinterScriptableStream</a>



<a href="/windows-hardware/drivers/print/v4-driver-property-bags">V4 Printer Driver Property Bags</a>
