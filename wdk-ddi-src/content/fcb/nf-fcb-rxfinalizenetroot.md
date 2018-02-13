---
UID: NF:fcb.RxFinalizeNetRoot
title: RxFinalizeNetRoot function
author: windows-driver-content
description: RxFinalizeNetRoot finalizes the given NET_ROOT structure. The caller must have an exclusive lock on the netname table associated with the device object.
old-location: ifsk\rxfinalizenetroot.htm
old-project: ifsk
ms.assetid: f0566902-b85b-4676-9f8f-67749ce2060a
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: rxref_66fb454b-96a0-401b-b184-0c24510bfaf6.xml, ifsk.rxfinalizenetroot, RxFinalizeNetRoot, RxFinalizeNetRoot function [Installable File System Drivers], fcb/RxFinalizeNetRoot
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fcb.h
req.include-header: Fcb.h, Mrxfcb.h
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
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	fcb.h
apiname:
-	RxFinalizeNetRoot
product: Windows
targetos: Windows
req.typenames: FA_ENTRY, *PFA_ENTRY
---

# RxFinalizeNetRoot function


## -description


<b>RxFinalizeNetRoot</b> finalizes the given NET_ROOT structure. The caller must have an exclusive lock on the netname table associated with the device object. 


## -syntax


````
BOOLEAN RxFinalizeNetRoot(
  _Out_ PNET_ROOT ThisNetRoot,
  _In_  BOOLEAN   RecursiveFinalize,
  _In_  BOOLEAN   ForceFinalize
);
````


## -parameters




### -param ThisNetRoot [out]

A pointer to the NET_ROOT structure to finalize.


### -param RecursiveFinalize [in]

The value indicating whether the finalization should be done recursively. 


### -param ForceFinalize [in]

The value indicating whether the finalization should be forced, regardless of the reference count. 

If <i>ForceFinalize</i> is <b>FALSE</b>, then the <b>NodeReferenceCount</b> member of the NET_ROOT strcuture pointed to by <i>ThisNetRoot </i>must be 1 for the NET_ROOT to be finalized. 


## -returns



<b>RxFinalizeNetRoot</b> returns <b>TRUE</b> on success or <b>FALSE</b> if the finalization did not occur: If a finalization of the NET_ROOT is already in process, <b>RxFinalizeNetRoot</b> will return <b>FALSE</b>.




## -remarks



The <b>RxFinalizeNetRoot</b> routine is not normally called by network mini-redirector drivers directly. RDBSS calls this routine internally when the reference count on the NET_ROOT is decremented to 1.

Before calling <b>RxFinalizeNetRoot</b>, a lock on the netname table associated with the device object must be acquired in exclusive mode. 

If the <i>RecursiveFinalize</i> parameter is <b>TRUE</b>, then <b>RxFinalizeNetRoot</b> will purge any orphaned FCB structures associated with this NET_ROOT. These ophaned FCBs are structures where the <b>FcbState</b> member has the FCB_STATE_ORPHANED flag set on. 




## -see-also

<a href="..\fcb\nf-fcb-rxcreatesrvopen.md">RxCreateSrvOpen</a>



<a href="..\fcb\nf-fcb-rxfinalizevnetroot.md">RxFinalizeVNetRoot</a>



<a href="..\fcb\nf-fcb-rxcreatenetfcb.md">RxCreateNetFcb</a>



<a href="..\rxprocs\nf-rxprocs-rxreference.md">RxReference</a>



<a href="..\fcb\nf-fcb-rxfinishfcbinitialization.md">RxFinishFcbInitialization</a>



<a href="..\fcb\nf-fcb-rxfinalizesrvopen.md">RxFinalizeSrvOpen</a>



<a href="..\fcb\nf-fcb-rxcreatevnetroot.md">RxCreateVNetRoot</a>



<a href="..\rxprocs\nf-rxprocs-rxforcefinalizeallvnetroots.md">RxForceFinalizeAllVNetRoots</a>



<a href="..\fcb\nf-fcb-rxcreatesrvcall.md">RxCreateSrvCall</a>



<a href="..\rxprocs\nf-rxprocs-rxfinalizeconnection.md">RxFinalizeConnection</a>



<a href="..\rxprocs\nf-rxprocs-rxsetsrvcalldomainname.md">RxSetSrvCallDomainName</a>



<a href="..\fcb\nf-fcb-rxcreatenetfobx.md">RxCreateNetFobx</a>



<a href="..\fcb\nf-fcb-rxfinalizesrvcall.md">RxFinalizeSrvCall</a>



<a href="..\fcb\nf-fcb-rxcreatenetroot.md">RxCreateNetRoot</a>



<a href="..\rxprocs\nf-rxprocs-rxdereference.md">RxDereference</a>



<a href="https://msdn.microsoft.com/f7846343-9af6-4b7f-9c8d-190abb524946">The NET_ROOT Structure</a>



<a href="..\rxprocs\nf-rxprocs-rxfinalizenetfcb.md">RxFinalizeNetFcb</a>



<a href="..\fcb\nf-fcb-rxpdereferencenetfcb.md">RxpDereferenceNetFcb</a>



<a href="..\fcb\nf-fcb-rxpreferencenetfcb.md">RxpReferenceNetFcb</a>



<a href="..\fcb\nf-fcb-rxfinalizenetfobx.md">RxFinalizeNetFobx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxFinalizeNetRoot function%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

