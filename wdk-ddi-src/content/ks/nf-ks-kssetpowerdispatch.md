---
UID: NF:ks.KsSetPowerDispatch
title: KsSetPowerDispatch function
author: windows-driver-content
description: Sets the power dispatch function to be called when the driver object receives an IRP_MJ_POWER IRP.
old-location: stream\kssetpowerdispatch.htm
old-project: stream
ms.assetid: 77ceaebe-ded1-4fbb-bc10-593ff62fcbe2
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ksfunc_b561e4ba-dadd-4e9c-a8e3-1d9b182cdd4f.xml, KsSetPowerDispatch, KsSetPowerDispatch routine [Streaming Media Devices], stream.kssetpowerdispatch, ks/KsSetPowerDispatch
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
-	KsSetPowerDispatch
product: Windows
targetos: Windows
req.typenames: 
---

# KsSetPowerDispatch function


## -description


Sets the power dispatch function to be called when the driver object receives an <b>IRP_MJ_POWER</b> IRP. This is only effective if <b>KsDefaultDispatchPower</b> is called to dispatch or complete power IRPs.

This has the effect of adding this object header to a list of object headers that have power dispatch routines to execute. The head of this list is kept by the device header. Assumes that the caller has previously allocated a device header on the underlying Device Object with <b>KsAllocateDeviceHeader</b>.


## -syntax


````
VOID KsSetPowerDispatch(
  _In_     KSOBJECT_HEADER       Header,
  _In_opt_ PFNKSCONTEXT_DISPATCH PowerDispatch ,
  _In_opt_ PVOID                 PowerContext 
);
````


## -parameters




### -param Header [in]

Points to a header previously allocated by <b>KsAllocateObjectHeader</b>.


### -param PowerDispatch [in, optional]

Optionally contains the power dispatch function that will be called, or <b>NULL</b> if the function is to be removed from the list of functions being called. This function must not complete the power IRP sent. The return value of this function must be STATUS_SUCCESS. <b>KsSetPowerDispatch</b> can be called while executing this power dispatch routine if the purpose is to manipulate this list entry only. Manipulating other list entries may confuse the current enumeration.


### -param PowerContext [in, optional]

Optionally contains the context parameter to pass to the power dispatch function.


## -returns


None



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff567164">KStrContextDispatch</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsSetPowerDispatch routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

