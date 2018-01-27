---
UID: NF:fcb.RxCreateSrvOpen
title: RxCreateSrvOpen function
author: windows-driver-content
description: RxCreateSrvOpen allocates, initializes, and inserts a new SRV_OPEN structure into the in-memory data structures used by RDBSS. If a new structure has to be allocated, it has space for an FOBX structure.
old-location: ifsk\rxcreatesrvopen.htm
old-project: ifsk
ms.assetid: e2cb8b92-2894-4515-bdf1-944c7f6ed3b0
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ifsk.rxcreatesrvopen, fcb/RxCreateSrvOpen, RxCreateSrvOpen, rxref_663bb1d7-f914-4571-9701-e21ccf548337.xml, RxCreateSrvOpen function [Installable File System Drivers]
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: <= APC_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	fcb.h
apiname: 
-	RxCreateSrvOpen
product: Windows
targetos: Windows
req.typenames: FA_ENTRY, *PFA_ENTRY
---

# RxCreateSrvOpen function


## -description


<b>RxCreateSrvOpen</b> allocates, initializes, and inserts a new SRV_OPEN structure into the in-memory data structures used by RDBSS. If a new structure has to be allocated, it has space for an FOBX structure. 


## -syntax


````
PSRV_OPEN RxCreateSrvOpen(
  _In_    PV_NET_ROOT VNetRoot,
  _Inout_ PFCB        Fcb
);
````


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

<a href="..\fcb\nf-fcb-rxfinalizenetfobx.md">RxFinalizeNetFobx</a>

<a href="..\rxprocs\nf-rxprocs-rxreference.md">RxReference</a>

<a href="..\fcb\nf-fcb-rxfinalizesrvcall.md">RxFinalizeSrvCall</a>

<a href="..\fcb\nf-fcb-rxpreferencenetfcb.md">RxpReferenceNetFcb</a>

<a href="https://msdn.microsoft.com/6cf4c6f6-a21f-4919-92b5-2403b650d8d0">The SRV_OPEN Structure</a>

<a href="..\fcb\nf-fcb-rxfinalizesrvopen.md">RxFinalizeSrvOpen</a>

<a href="..\fcb\nf-fcb-rxcreatenetfcb.md">RxCreateNetFcb</a>

<a href="..\rxprocs\nf-rxprocs-rxdereference.md">RxDereference</a>

<a href="..\fcb\nf-fcb-rxfinishfcbinitialization.md">RxFinishFcbInitialization</a>

<a href="..\fcb\nf-fcb-rxcreatesrvcall.md">RxCreateSrvCall</a>

<a href="..\fcb\nf-fcb-rxcreatenetfobx.md">RxCreateNetFobx</a>

<a href="..\fcb\nf-fcb-rxcreatevnetroot.md">RxCreateVNetRoot</a>

<a href="..\fcb\nf-fcb-rxcreatenetroot.md">RxCreateNetRoot</a>

<a href="..\rxprocs\nf-rxprocs-rxsetsrvcalldomainname.md">RxSetSrvCallDomainName</a>

<a href="..\fcb\nf-fcb-rxpdereferencenetfcb.md">RxpDereferenceNetFcb</a>

<a href="..\fcb\nf-fcb-rxfinalizevnetroot.md">RxFinalizeVNetRoot</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-fcb-structure">The FCB Structure</a>

<a href="..\fcb\nf-fcb-rxfinalizenetroot.md">RxFinalizeNetRoot</a>

<a href="..\rxprocs\nf-rxprocs-rxfinalizeconnection.md">RxFinalizeConnection</a>

<a href="https://msdn.microsoft.com/866eba91-13b6-4b15-93de-4f627a635c92">The V_NET_ROOT Structure</a>

<a href="..\rxprocs\nf-rxprocs-rxfinalizenetfcb.md">RxFinalizeNetFcb</a>

<a href="..\rxprocs\nf-rxprocs-rxforcefinalizeallvnetroots.md">RxForceFinalizeAllVNetRoots</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxCreateSrvOpen function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

