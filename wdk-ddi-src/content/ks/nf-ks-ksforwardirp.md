---
UID: NF:ks.KsForwardIrp
title: KsForwardIrp function (ks.h)
description: The KsForwardIrp function forwards an IRP to the specified driver after initializing the next stack location and setting the file object.
old-location: stream\ksforwardirp.htm
tech.root: stream
ms.assetid: 6db0c232-d90b-4187-94c0-a840f87cf999
ms.date: 04/23/2018
keywords: ["KsForwardIrp function"]
ms.keywords: KsForwardIrp, KsForwardIrp function [Streaming Media Devices], ks/KsForwardIrp, ksfunc_cc7908b4-a6f2-40b1-990f-22c7b5e2bda2.xml, stream.ksforwardirp
f1_keywords:
 - "ks/KsForwardIrp"
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsForwardIrp
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsForwardIrp function


## -description


The <b>KsForwardIrp</b> function forwards an IRP to the specified driver after initializing the next stack location and setting the file object. 


## -parameters




### -param Irp [in]

Specifies the IRP that is being forwarded to the specified driver.


### -param FileObject [in]

Specifies the file object to initialize the next stack with.


### -param ReuseStackLocation [in]

Specifies the new stack location.


## -returns



The <b>KsForwardIrp</b> function returns the result of the <b>IoCallDriver</b>, or it returns an invalid status if no more stack depth is available.




## -remarks



Use the <b>KsForwardIrp</b> function when only the <i>FileObject</i> parameter of the forwarded IRP changes when the current stack parameters are copied to the next stack location. The function verifies that there is a new stack location to copy into before attempting to copy. If there is no new stack location, the IRP is completed with STATUS_INVALID_DEVICE_REQUEST.



