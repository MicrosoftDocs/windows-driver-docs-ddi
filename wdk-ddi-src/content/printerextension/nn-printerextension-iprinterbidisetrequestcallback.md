---
UID: NN:printerextension.IPrinterBidiSetRequestCallback
title: IPrinterBidiSetRequestCallback (printerextension.h)
description: Describes the signature of the callback object that receives the Bidi response.
tech.root: print
ms.date: 08/02/2022
keywords: ["IPrinterBidiSetRequestCallback interface"]
ms.keywords: IPrinterBidiSetRequestCallback, IPrinterBidiSetRequestCallback interface [Print Devices], IPrinterBidiSetRequestCallback interface [Print Devices],described, print.iprinterbidisetrequestcallback, printerextension/IPrinterBidiSetRequestCallback
req.header: printerextension.h
req.include-header: Printerextension.h
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

## -description

Describes the signature of the callback object that receives the Bidi response.

## -inheritance

The **IPrinterBidiSetRequestCallback** interface inherits from the [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) interface.

## -remarks

**IPrinterBidiSetRequestCallback** provides the Bidi response string, and **HRESULT** value returned from the [IBidiSpl2::SendRecvXmlString](../bidispl/nf-bidispl-ibidispl2-sendrecvxmlstring.md) method. In other words,  this interface provides the results of the attempt to send data to the device.

**IPrinterBidiSetRequestCallback**  helps to make it possible to perform device maintenance from a UWP  device app or from a printer extension. For more information, see [Device Maintenance](/windows-hardware/drivers/print/device-maintenance).

## -see-also

[Device Maintenance](/windows-hardware/drivers/print/device-maintenance)

[IBidiSpl2::SendRecvXmlString](../bidispl/nf-bidispl-ibidispl2-sendrecvxmlstring.md)

[SendBidiSetRequestAsync](./nf-printerextension-iprinterqueue2-sendbidisetrequestasync.md)
