---
UID: NF:ks.KsRemoveSpecificIrpFromCancelableQueue
title: KsRemoveSpecificIrpFromCancelableQueue function (ks.h)
description: The KsRemoveSpecificIrpFromCancelableQueue function removes the specified IRP from the specified queue. This is performed on an IRP that was previously acquired using KsRemoveIrpFromCancelableQueue, but that was not actually removed from the queue.
old-location: stream\ksremovespecificirpfromcancelablequeue.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KsRemoveSpecificIrpFromCancelableQueue function"]
ms.keywords: KsRemoveSpecificIrpFromCancelableQueue, KsRemoveSpecificIrpFromCancelableQueue function [Streaming Media Devices], ks/KsRemoveSpecificIrpFromCancelableQueue, ksfunc_db7aeb28-a39d-4ab6-9df5-6eef83453c85.xml, stream.ksremovespecificirpfromcancelablequeue
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
targetos: Windows
req.typenames: 
f1_keywords:
 - KsRemoveSpecificIrpFromCancelableQueue
 - ks/KsRemoveSpecificIrpFromCancelableQueue
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsRemoveSpecificIrpFromCancelableQueue
---

# KsRemoveSpecificIrpFromCancelableQueue function


## -description

The <b>KsRemoveSpecificIrpFromCancelableQueue</b> function removes the specified IRP from the specified queue. This is performed on an IRP that was previously acquired using <a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksremoveirpfromcancelablequeue">KsRemoveIrpFromCancelableQueue</a>, but that was not actually removed from the queue.

## -parameters

### -param Irp [in]


Points to I/O request packet.

## -returns

None
