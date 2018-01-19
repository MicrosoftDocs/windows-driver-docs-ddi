---
UID: NC:ks.PFNKSFILTERIRP
title: PFNKSFILTERIRP
author: windows-driver-content
description: An AVStream minidriver's AVStrMiniFilterCreate routine is called when a filter receives an IRP.
old-location: stream\avstrminifiltercreate.htm
old-project: stream
ms.assetid: c654e822-a932-4da0-ab11-4669bd8ba4b4
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: NpdBrokerUninitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MyAVStrMiniFilterIRPHandler
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
req.irql: PASSIVE_LEVEL (See Remarks section)
req.typenames: KEYWORDSELECTOR
---

# PFNKSFILTERIRP callback



## -description
An AVStream minidriver's <i>AVStrMiniFilterCreate</i> routine is called when a filter receives an IRP. 


<a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550720">IRP_MJ_CLOSE</a>




## -prototype

````
PFNKSFILTERIRP MyAVStrMiniFilterIRPHandler;

NTSTATUS MyAVStrMiniFilterIRPHandler(
  _In_ PKSFILTER Filter,
  _In_ PIRP      Irp
)
{ ... }
````


## -parameters

### -param Filter [in]

Pointer to the <a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a>.


### -param Irp [in]

Pointer to the IRP for <i>Filter</i>.


## -returns
If the routine succeeds, return STATUS_SUCCESS or the error code.


## -remarks
Typically, this routine is used by minidrivers that want to initialize the context and resources associated with the filter.

The minidriver specifies this routine's address in the <b>Create</b> member of its <a href="..\ks\ns-ks-_ksfilter_dispatch.md">KSFILTER_DISPATCH</a> structure.

At the point at which the routine is called, the file object has an associated context, and the KS object header has been allocated.

This routine is called at IRQL = PASSIVE_LEVEL with the device mutex held.

This routine is optional.

The minidriver specifies this routine's address in the <b>Close</b> member of its <a href="..\ks\ns-ks-_ksfilter_dispatch.md">KSFILTER_DISPATCH</a> structure.

At the point at which the routine is called, any registered events on the filter have been freed, but the object is otherwise intact.

This routine is called at IRQL = PASSIVE_LEVEL with the device mutex held. For more information about mutexes, see <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.

Return STATUS_SUCCESS or STATUS_PENDING. If a minidriver returns STATUS_PENDING, AVStream will not complete the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550720">IRP_MJ_CLOSE</a> immediately. Before returning STATUS_PENDING, however, the minidriver must call <a href="..\wdm\nf-wdm-iomarkirppending.md">IoMarkIrpPending</a>. Once the processing of the close is complete, the minidriver must set the IRP's status code and then call <a href="..\ks\nf-ks-kscompletependingrequest.md">KsCompletePendingRequest</a>.


## -see-also
<dl>
<dt>
<a href="..\ks\ns-ks-_ksfilter_dispatch.md">KSFILTER_DISPATCH</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iomarkirppending.md">IoMarkIrpPending</a>
</dt>
<dt>
<a href="..\ks\nf-ks-kscompletependingrequest.md">KsCompletePendingRequest</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20PFNKSFILTERIRP routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

