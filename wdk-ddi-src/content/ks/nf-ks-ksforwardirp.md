---
UID: NF:ks.KsForwardIrp
title: KsForwardIrp function
author: windows-driver-content
description: The KsForwardIrp function forwards an IRP to the specified driver after initializing the next stack location and setting the file object.
old-location: stream\ksforwardirp.htm
old-project: stream
ms.assetid: 6db0c232-d90b-4187-94c0-a840f87cf999
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ks/KsForwardIrp, stream.ksforwardirp, KsForwardIrp, ksfunc_cc7908b4-a6f2-40b1-990f-22c7b5e2bda2.xml, KsForwardIrp function [Streaming Media Devices]
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	LibDef
apilocation: 
-	Ks.lib
-	Ks.dll
apiname: 
-	KsForwardIrp
product: Windows
targetos: Windows
req.typenames: 
---

# KsForwardIrp function


## -description


The <b>KsForwardIrp</b> function forwards an IRP to the specified driver after initializing the next stack location and setting the file object. 


## -syntax


````
NTSTATUS KsForwardIrp(
  _In_ PIRP         Irp,
  _In_ PFILE_OBJECT FileObject,
  _In_ BOOLEAN      ReuseStackLocation
);
````


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


