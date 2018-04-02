---
UID: NF:fcb.RxCreateSrvOpen
title: RxCreateSrvOpen function
author: windows-driver-content
description: RxCreateSrvOpen allocates, initializes, and inserts a new SRV_OPEN structure into the in-memory data structures used by RDBSS. If a new structure has to be allocated, it has space for an FOBX structure.
old-location: ifsk\rxcreatesrvopen.htm
old-project: ifsk
ms.assetid: e2cb8b92-2894-4515-bdf1-944c7f6ed3b0
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: RxCreateSrvOpen, RxCreateSrvOpen function [Installable File System Drivers], fcb/RxCreateSrvOpen, ifsk.rxcreatesrvopen, rxref_663bb1d7-f914-4571-9701-e21ccf548337.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fcb.h
req.include-header: Mrxfcb.h, Fcb.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	fcb.h
api_name:
-	RxCreateSrvOpen
product: Windows
targetos: Windows
req.typenames: FA_ENTRY, *PFA_ENTRY
---

# RxCreateSrvOpen function


## -description


<b>RxCreateSrvOpen</b> allocates, initializes, and inserts a new SRV_OPEN structure into the in-memory data structures used by RDBSS. If a new structure has to be allocated, it has space for an FOBX structure. 


## -parameters




### -param VNetRoot [in]

A pointer to the V_NET_ROOT structure.


### -param Fcb [in, out]

A pointer to the associated FCB structure.


## -returns



<b>RxCreateSrvOpen</b> returns a pointer to a newly created SRV_OPEN data structure on success or a <b>NULL</b> pointer on failure. 




## -remarks



The <b>RxCreateSrvOpen</b> routine is not normally called by network mini-redirector drivers directly. RDBSS calls this routine internally when an I/O request packet is received for IRP_MJ_CREATE and a SRV_OPEN needs to be created. This IRP is normally received by RDBSS in response to a user-mode application requesting a file create operation on a network share. It is also possible for another kernel driver to issue such an IRP. 

Before calling <b>RxCreateSrvOpen</b>, a lock on the associated FCB structure must be acquired in exclusive mode. 

<b>RxCreateSrvOpen </b>will try and use the SRV_CALL allocated as part of the associated FCB structure if it is available. If the SRV_CALL allocated with the FCB is not available, then <b>RxCreateSrvOpen</b> will allocate a new SRV_CALL structure. 

If the associated FCB is a paging file, <b>RxCreateSrvOpen</b> allocates non-paged pool memory when creating the new SRV_OPEN data structure. If the associated FCB is a not a paging file, <b>RxCreateSrvOpen</b> allocates paged pool memory when creating the new SRV_OPEN data structure.

Windows does not currently allow having a paging file on a remote machine. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554356">RxCreateNetFcb</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554358">RxCreateNetFobx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554366">RxCreateNetRoot</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554370">RxCreateSrvCall</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554380">RxCreateVNetRoot</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554388">RxDereference</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554409">RxFinalizeConnection</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554412">RxFinalizeNetFcb</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554418">RxFinalizeNetFobx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554421">RxFinalizeNetRoot</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554426">RxFinalizeSrvCall</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554432">RxFinalizeSrvOpen</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554450">RxFinalizeVNetRoot</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554454">RxFinishFcbInitialization</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554463">RxForceFinalizeAllVNetRoots</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554688">RxReference</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554728">RxSetSrvCallDomainName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554608">RxpDereferenceNetFcb</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554627">RxpReferenceNetFcb</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-fcb-structure">The FCB Structure</a>



<a href="https://msdn.microsoft.com/6cf4c6f6-a21f-4919-92b5-2403b650d8d0">The SRV_OPEN Structure</a>



<a href="https://msdn.microsoft.com/866eba91-13b6-4b15-93de-4f627a635c92">The V_NET_ROOT Structure</a>
 

 

