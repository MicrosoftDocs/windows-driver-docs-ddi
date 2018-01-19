---
UID: NF:ks.KsDispatchSpecificMethod
title: KsDispatchSpecificMethod function
author: windows-driver-content
description: The KsDispatchSpecificMethod function dispatches a method to a specific handler. The function assumes that the caller has previously dispatched the IRP to a handler through the KsMethodHandler function. The function can only be called at PASSIVE_LEVEL.
old-location: stream\ksdispatchspecificmethod.htm
old-project: stream
ms.assetid: d23ba3a3-9fcf-46a5-88dd-42af389c8598
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsDispatchSpecificMethod
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KsDispatchSpecificMethod
req.alt-loc: Ks.lib,Ks.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ks.lib
req.dll: 
req.irql: 
req.typenames: 
---

# KsDispatchSpecificMethod function



## -description
The <b>KsDispatchSpecificMethod</b> function dispatches a method to a specific handler. The function assumes that the caller has previously dispatched the IRP to a handler through the <b>KsMethodHandler</b> function. 

The function can only be called at PASSIVE_LEVEL.



## -syntax

````
NTSTATUS KsDispatchSpecificMethod(
  _In_ PIRP         Irp,
  _In_ PFNKSHANDLER Handler
);
````


## -parameters

### -param Irp [in]

Specifies the IRP with the method request being dispatched.


### -param Handler [in]

Specifies the pointer to the specific method handler.


## -returns
The <b>KsDispatchSpecificMethod</b> function returns STATUS_SUCCESS if successful, or if unsuccessful it returns an error. 


## -remarks
The <b>KsDispatchSpecificMethod</b> function is intended for additional processing of the method such as completing a pending operation.


## -see-also
<dl>
<dt>
<a href="..\ks\nf-ks-ksmethodhandler.md">KsMethodHandler</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsDispatchSpecificMethod function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

