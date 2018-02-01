---
UID: NF:wdfobject.WdfObjectGetTypedContextWorker
title: WdfObjectGetTypedContextWorker function
author: windows-driver-content
description: The WdfObjectGetTypedContextWorker method is reserved for internal use only. Use the WdfObjectGetTypedContext macro instead.
old-location: wdf\wdfobjectgettypedcontextworker.htm
old-project: wdf
ms.assetid: 1d95084b-16c4-468e-84af-47650292c5a1
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: kmdf.wdfobjectgettypedcontextworker, wdfobject/WdfObjectGetTypedContextWorker, wdf.wdfobjectgettypedcontextworker, DFGenObjectRef_d932d163-5341-45b3-b896-bb3adb5831a6.xml, WdfObjectGetTypedContextWorker, WdfObjectGetTypedContextWorker method
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfobject.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfobject.h
apiname:
-	WdfObjectGetTypedContextWorker
product: Windows
targetos: Windows
req.typenames: WDF_SYNCHRONIZATION_SCOPE
req.product: Windows 10 or later.
---

# WdfObjectGetTypedContextWorker function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfObjectGetTypedContextWorker</b> method is reserved for internal use only. Use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548749">WdfObjectGetTypedContext</a> macro instead.


## -syntax


````
PVOID WdfObjectGetTypedContextWorker(
  _In_ WDFOBJECT                      Handle,
  _In_ PCWDF_OBJECT_CONTEXT_TYPE_INFO TypeInfo
);
````


## -parameters




### -param Handle [in]



### -param TypeInfo [in]


