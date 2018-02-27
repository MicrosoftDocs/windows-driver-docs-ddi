---
UID: NF:printerextension.IPrinterExtensionEvent.OnPrinterQueuesEnumerated
title: IPrinterExtensionEvent::OnPrinterQueuesEnumerated method
author: windows-driver-content
description: Called when printer queues are enumerated.
old-location: print\iprinterextensionevent_onprinterqueuesenumerated.htm
old-project: print
ms.assetid: 947063C6-563A-4BB7-918E-479941B4583F
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IPrinterExtensionEvent, IPrinterExtensionEvent interface [Print Devices], OnPrinterQueuesEnumerated method, IPrinterExtensionEvent::OnPrinterQueuesEnumerated, OnPrinterQueuesEnumerated method [Print Devices], OnPrinterQueuesEnumerated method [Print Devices], IPrinterExtensionEvent interface, OnPrinterQueuesEnumerated,IPrinterExtensionEvent.OnPrinterQueuesEnumerated, print.iprinterextensionevent_onprinterqueuesenumerated, printerextension/IPrinterExtensionEvent::OnPrinterQueuesEnumerated
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
-	IPrinterExtensionEvent.OnPrinterQueuesEnumerated
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrinterExtensionEvent::OnPrinterQueuesEnumerated method


## -description


Called when printer queues are enumerated.


## -syntax


````
HRESULT OnPrinterQueuesEnumerated(
  [in] IPrinterExtensionContextCollection *pContextCollection
);
````


## -parameters




### -param pContextCollection [in]

Pointer to <a href="..\printerextension\nn-printerextension-iprinterextensioncontextcollection.md">IPrinterExtensionContextCollection</a> object.


## -returns



This method returns an <b>HRESULT</b> value.




## -remarks



<b>OnPrinterQueuesEnumerated</b> is called every time the set of print queues associated with the printer extension is updated. So it is important for printer extensions to be able to handle multiple calls to this method without causing a catastrophic failure of the printer extension.




## -see-also

<a href="..\printerextension\nn-printerextension-iprinterextensionevent.md">IPrinterExtensionEvent</a>



<a href="..\printerextension\nn-printerextension-iprinterextensioncontextcollection.md">IPrinterExtensionContextCollection</a>



<a href="..\printerextension\nn-printerextension-iprinterextensioncontext.md">IPrinterExtensionContext</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterExtensionEvent::OnPrinterQueuesEnumerated method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

