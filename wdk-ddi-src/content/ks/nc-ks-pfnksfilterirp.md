---
UID: NC:ks.PFNKSFILTERIRP
title: PFNKSFILTERIRP
author: windows-driver-content
description: An AVStream minidriver's AVStrMiniFilterCreate routine is called when a filter receives an IRP.
old-location: stream\avstrminifiltercreate.htm
tech.root: stream
ms.assetid: c654e822-a932-4da0-ab11-4669bd8ba4b4
ms.date: 4/23/2018
ms.keywords: AVStrMiniFilterClose, AVStrMiniFilterCreate, MyAVStrMiniFilterIRPHandler, MyAVStrMiniFilterIRPHandler routine [Streaming Media Devices], PFNKSFILTERIRP, avstclbk_76b73509-587e-47bd-9de7-92eac4237706.xml, ks/MyAVStrMiniFilterIRPHandler, stream.avstrminifiltercreate
ms.topic: callback
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (See Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	ks.h
api_name:
-	MyAVStrMiniFilterIRPHandler
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFNKSFILTERIRP callback function


## -description


An AVStream minidriver's <i>AVStrMiniFilterCreate</i> routine is called when a filter receives an IRP. 


<a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550720">IRP_MJ_CLOSE</a>



## -parameters




### -param Filter [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562522">KSFILTER</a>.


### -param Irp [in]

Pointer to the IRP for <i>Filter</i>.


## -returns



If the routine succeeds, return STATUS_SUCCESS or the error code.




## -remarks



<table>
<tr>
<th>IRP</th>
<th>Description</th>
</tr>
<tr>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a>
</td>
<td>
Typically, this routine is used by minidrivers that want to initialize the context and resources associated with the filter.

The minidriver specifies this routine's address in the <b>Create</b> member of its <a href="https://msdn.microsoft.com/library/windows/hardware/ff562554">KSFILTER_DISPATCH</a> structure.

At the point at which the routine is called, the file object has an associated context, and the KS object header has been allocated.

This routine is called at IRQL = PASSIVE_LEVEL with the device mutex held.</p>If the routine succeeds, the create operation is guaranteed to succeed. Return STATUS_SUCCESS or the error code that was returned from the attempt to create the filter. STATUS_PENDING is also a legal return code. If a minidriver returns STATUS_PENDING, AVStream will not complete the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a> immediately. Before returning STATUS_PENDING, the minidriver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549422">IoMarkIrpPending</a>. When the processing of the create is complete, the minidriver must set the IRP's status code and then call <a href="https://msdn.microsoft.com/library/windows/hardware/ff561025">KsCompletePendingRequest</a>.
        This routine is optional.

</td>
</tr>
<tr>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550720">IRP_MJ_CLOSE</a>
</td>
<td>
The minidriver specifies this routine's address in the <b>Close</b> member of its <a href="https://msdn.microsoft.com/library/windows/hardware/ff562554">KSFILTER_DISPATCH</a> structure.

At the point at which the routine is called, any registered events on the filter have been freed, but the object is otherwise intact.

This routine is called at IRQL = PASSIVE_LEVEL with the device mutex held. For more information about mutexes, see <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.

This routine is optional.

Return STATUS_SUCCESS or STATUS_PENDING. If a minidriver returns STATUS_PENDING, AVStream will not complete the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550720">IRP_MJ_CLOSE</a> immediately. Before returning STATUS_PENDING, however, the minidriver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549422">IoMarkIrpPending</a>. Once the processing of the close is complete, the minidriver must set the IRP's status code and then call <a href="https://msdn.microsoft.com/library/windows/hardware/ff561025">KsCompletePendingRequest</a>.

</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549422">IoMarkIrpPending</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562554">KSFILTER_DISPATCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561025">KsCompletePendingRequest</a>
 

 

