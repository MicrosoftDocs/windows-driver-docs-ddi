---
UID: NF:ks.KsDispatchSpecificMethod
title: KsDispatchSpecificMethod function
author: windows-driver-content
description: The KsDispatchSpecificMethod function dispatches a method to a specific handler. The function assumes that the caller has previously dispatched the IRP to a handler through the KsMethodHandler function. The function can only be called at PASSIVE_LEVEL.
old-location: stream\ksdispatchspecificmethod.htm
tech.root: stream
ms.assetid: d23ba3a3-9fcf-46a5-88dd-42af389c8598
ms.date: 04/23/2018
ms.keywords: KsDispatchSpecificMethod, KsDispatchSpecificMethod function [Streaming Media Devices], ks/KsDispatchSpecificMethod, ksfunc_9304d127-8930-4e0e-b39f-aefc10e54131.xml, stream.ksdispatchspecificmethod
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsDispatchSpecificMethod
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsDispatchSpecificMethod function


## -description


The <b>KsDispatchSpecificMethod</b> function dispatches a method to a specific handler. The function assumes that the caller has previously dispatched the IRP to a handler through the <b>KsMethodHandler</b> function. 

The function can only be called at PASSIVE_LEVEL.


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563399">KsMethodHandler</a>
 

 

