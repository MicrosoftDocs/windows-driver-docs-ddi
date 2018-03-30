---
UID: NF:printerextension.IPrinterExtensionEvent.OnPrinterQueuesEnumerated
title: IPrinterExtensionEvent::OnPrinterQueuesEnumerated method
author: windows-driver-content
description: Called when printer queues are enumerated.
old-location: print\iprinterextensionevent_onprinterqueuesenumerated.htm
old-project: print
ms.assetid: 947063C6-563A-4BB7-918E-479941B4583F
ms.author: windowsdriverdev
ms.date: 2/26/2018
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
-	IPrinterExtensionEvent.OnPrinterQueuesEnumerated
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrinterExtensionEvent::OnPrinterQueuesEnumerated method


## -description


Called when printer queues are enumerated.


## -parameters




### -param pContextCollection [in]

Pointer to <a href="https://msdn.microsoft.com/library/windows/hardware/hh846191">IPrinterExtensionContextCollection</a> object.


## -returns



This method returns an <b>HRESULT</b> value.




## -remarks



<b>OnPrinterQueuesEnumerated</b> is called every time the set of print queues associated with the printer extension is updated. So it is important for printer extensions to be able to handle multiple calls to this method without causing a catastrophic failure of the printer extension.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh406649">IPrinterExtensionContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh846191">IPrinterExtensionContextCollection</a>



<a href="https://msdn.microsoft.com/A0F4DB51-D68E-4516-833A-7E984247796B">IPrinterExtensionEvent</a>
 

 

