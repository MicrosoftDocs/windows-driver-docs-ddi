---
UID: NF:ks.KsCompletePendingRequest
title: KsCompletePendingRequest function (ks.h)
description: The KsCompletePendingRequest function is used to complete an I/O request in response to which an AVStream dispatch function previously returned STATUS_PENDING.
old-location: stream\kscompletependingrequest.htm
tech.root: stream
ms.assetid: 9bde557e-0759-4f5b-989e-a34a701d2ebd
ms.date: 04/23/2018
ms.keywords: KsCompletePendingRequest, KsCompletePendingRequest function [Streaming Media Devices], avfunc_e01e61fc-ec10-4781-aee2-0aa7e24ca31a.xml, ks/KsCompletePendingRequest, stream.kscompletependingrequest
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsCompletePendingRequest
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsCompletePendingRequest function


## -description


The<b> KsCompletePendingRequest</b> function is used to complete an I/O request in response to which an AVStream dispatch function previously returned STATUS_PENDING.


## -parameters




### -param Irp [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a> structure that must be completed; this is passed in the dispatch function that returned a STATUS_PENDING.


## -returns



None




## -remarks



If the dispatch function in question does not pass an IRP, it <b>cannot</b> return STATUS_PENDING. Minidrivers should set <b>IRP.IoStatus.Status</b> before calling this function.

<b>KsCompletePendingRequest</b> can be used for PnP dispatch functions in the device dispatch table or filter creation and closure requests. Dispatch functions that return STATUS_PENDING must call this function when they complete the request. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550671">IO_STATUS_BLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561693">KSDEVICE_DISPATCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562554">KSFILTER_DISPATCH</a>
 

 

