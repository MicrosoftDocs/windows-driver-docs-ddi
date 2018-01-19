---
UID: NC:ks.PFNKSCONTEXT_DISPATCH
title: PFNKSCONTEXT_DISPATCH
author: windows-driver-content
description: A streaming minidriver's KStrContextDispatch routine is called to process IRP_MJ_POWER IRPs.
old-location: stream\kstrcontextdispatch.htm
old-project: stream
ms.assetid: be96eb59-6128-41bd-ad31-38f0d1a4e656
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: NpdBrokerUninitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KStrContextDispatch
req.alt-loc: ks.h
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
req.typenames: KEYWORDSELECTOR
---

# PFNKSCONTEXT_DISPATCH callback



## -description
A streaming minidriver's <i>KStrContextDispatch</i> routine is called to process IRP_MJ_POWER IRPs.



## -prototype

````
PFNKSCONTEXT_DISPATCH KStrContextDispatch;

NTSTATUS KStrContextDispatch(
  _In_ PVOID Context,
  _In_ PIRP  Irp
)
{ ... }
````


## -parameters

### -param Context [in]

Specifies the user-supplied memory context to be passed as the <i>PowerContext</i> argument to the <a href="..\ks\nf-ks-kssetpowerdispatch.md">KsSetPowerDispatch</a> function.


### -param Irp [in]

Specifies the power IRP to be processed.


## -returns
Returns STATUS_SUCCESS.


## -remarks
<i>KStrContextDispatch</i> must not complete the power IRP that is passed in the <i>Irp</i> parameter.

To manipulate the list entry only, <i>KStrContextDispatch</i> can call<b> KsSetPowerDispatch</b> while processing the power IRP. Manipulating other list entries can cause enumeration errors.


## -see-also
<dl>
<dt>
<a href="..\ks\nf-ks-kssetpowerdispatch.md">KsSetPowerDispatch</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KStrContextDispatch routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

