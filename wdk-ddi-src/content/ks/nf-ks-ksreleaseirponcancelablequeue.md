---
UID: NF:ks.KsReleaseIrpOnCancelableQueue
title: KsReleaseIrpOnCancelableQueue function
author: windows-driver-content
description: The KsReleaseIrpOnCancelableQueue function releases an acquired IRP that is already on a queue that can be canceled.
old-location: stream\ksreleaseirponcancelablequeue.htm
old-project: stream
ms.assetid: 797e0821-2354-4dd5-b2ee-428d654feb40
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ks/KsReleaseIrpOnCancelableQueue, KsReleaseIrpOnCancelableQueue, stream.ksreleaseirponcancelablequeue, KsReleaseIrpOnCancelableQueue function [Streaming Media Devices], ksfunc_90599c85-7874-4eca-9177-45dcacbeacc7.xml
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
-	KsReleaseIrpOnCancelableQueue
product: Windows
targetos: Windows
req.typenames: 
---

# KsReleaseIrpOnCancelableQueue function


## -description


The <b>KsReleaseIrpOnCancelableQueue</b> function releases an acquired IRP that is already on a queue that can be canceled. The function sets the cancel function and completes the canceling of the IRP, if necessary. The function can be called at IRQ level DISPATCH_LEVEL or lower.


## -syntax


````
VOID KsReleaseIrpOnCancelableQueue(
  _In_     PIRP           Irp,
  _In_opt_ PDRIVER_CANCEL DriverCancel
);
````


## -parameters




### -param Irp [in]

Specifies the IRP to release.


### -param DriverCancel [in, optional]

Optional parameter that specifies the cancel routine to use. If this is <b>NULL</b>, the standard <b>KsCancelRoutine</b> is used.


## -returns



None



