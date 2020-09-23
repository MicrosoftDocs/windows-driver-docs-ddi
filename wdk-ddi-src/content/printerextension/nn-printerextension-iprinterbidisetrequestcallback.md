---
UID: NN:printerextension.IPrinterBidiSetRequestCallback
title: IPrinterBidiSetRequestCallback (printerextension.h)
description: Describes the signature of the callback object that receives the Bidi response.
old-location: print\iprinterbidisetrequestcallback.htm
tech.root: print
ms.assetid: C85690D0-3CA7-46C7-B597-E36555879F08
ms.date: 04/20/2018
keywords: ["IPrinterBidiSetRequestCallback interface"]
ms.keywords: IPrinterBidiSetRequestCallback, IPrinterBidiSetRequestCallback interface [Print Devices], IPrinterBidiSetRequestCallback interface [Print Devices],described, print.iprinterbidisetrequestcallback, printerextension/IPrinterBidiSetRequestCallback
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
 - IPrinterBidiSetRequestCallback
 - printerextension/IPrinterBidiSetRequestCallback
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Printerextension.h
api_name:
 - IPrinterBidiSetRequestCallback
---

# IPrinterBidiSetRequestCallback interface


## -description

Describes the signature of the callback object that receives the Bidi response.

## -inheritance

The <b xmlns:loc="https://microsoft.com/wdcml/l10n">IPrinterBidiSetRequestCallback</b> interface inherits from the <a href="/windows/win32/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IPrinterBidiSetRequestCallback</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -remarks

<b>IPrinterBidiSetRequestCallback</b> provides the Bidi response string, and <b>HRESULT</b> value returned from the <a href="/windows-hardware/drivers/ddi/bidispl/nf-bidispl-ibidispl2-sendrecvxmlstring">IBidiSpl2::SendRecvXmlString</a> method. In other words,  this interface provides the results of the attempt to send data to the device. 

<b>IPrinterBidiSetRequestCallback</b>  helps to make it possible to perform device maintenance from a UWP  device app or from a printer extension. For more information, see <a href="/windows-hardware/drivers/print/device-maintenance">Device Maintenance</a>.

## -see-also

<a href="/windows-hardware/drivers/print/device-maintenance">Device Maintenance</a>



<a href="/windows-hardware/drivers/ddi/bidispl/nf-bidispl-ibidispl2-sendrecvxmlstring">IBidiSpl2::SendRecvXmlString</a>



<a href="/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprinterqueue2-sendbidisetrequestasync">SendBidiSetRequestAsync</a>