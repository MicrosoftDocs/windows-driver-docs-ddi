---
UID: NF:printerextension.IPrinterExtensionEvent.OnPrinterQueuesEnumerated
title: IPrinterExtensionEvent::OnPrinterQueuesEnumerated (printerextension.h)
description: Called when printer queues are enumerated.
old-location: print\iprinterextensionevent_onprinterqueuesenumerated.htm
tech.root: print
ms.assetid: 947063C6-563A-4BB7-918E-479941B4583F
ms.date: 04/20/2018
ms.keywords: IPrinterExtensionEvent interface [Print Devices],OnPrinterQueuesEnumerated method, IPrinterExtensionEvent.OnPrinterQueuesEnumerated, IPrinterExtensionEvent::OnPrinterQueuesEnumerated, OnPrinterQueuesEnumerated, OnPrinterQueuesEnumerated method [Print Devices], OnPrinterQueuesEnumerated method [Print Devices],IPrinterExtensionEvent interface, print.iprinterextensionevent_onprinterqueuesenumerated, printerextension/IPrinterExtensionEvent::OnPrinterQueuesEnumerated
f1_keywords:
 - "printerextension/IPrinterExtensionEvent.OnPrinterQueuesEnumerated"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Printerextension.h
api_name:
- IPrinterExtensionEvent.OnPrinterQueuesEnumerated
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrinterExtensionEvent::OnPrinterQueuesEnumerated


## -description


Called when printer queues are enumerated.


## -parameters




### -param pContextCollection [in]

Pointer to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprinterextensioncontextcollection">IPrinterExtensionContextCollection</a> object.


## -returns



This method returns an <b>HRESULT</b> value.




## -remarks



<b>OnPrinterQueuesEnumerated</b> is called every time the set of print queues associated with the printer extension is updated. So it is important for printer extensions to be able to handle multiple calls to this method without causing a catastrophic failure of the printer extension.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprinterextensioncontext">IPrinterExtensionContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprinterextensioncontextcollection">IPrinterExtensionContextCollection</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nn-printerextension-iprinterextensionevent">IPrinterExtensionEvent</a>
 

 

