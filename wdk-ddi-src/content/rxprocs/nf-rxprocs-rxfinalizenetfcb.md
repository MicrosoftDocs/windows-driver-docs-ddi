---
UID: NF:rxprocs.RxFinalizeNetFcb
title: RxFinalizeNetFcb function
author: windows-driver-content
description: RxFinalizeNetFCB finalizes the given FCB structure. The caller must have an exclusive lock on the NET_ROOT associated with FCB.
old-location: ifsk\rxfinalizenetfcb.htm
old-project: ifsk
ms.assetid: 1eed44e2-f9ed-45a1-a5fa-dbf6a9c7c703
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , F, N, R, RxFinalizeNetFcb, RxFinalizeNetFcb function [Installable File System Drivers], a, b, c, e, i, ifsk.rxfinalizenetfcb, l, n, rxprocs/RxFinalizeNetFcb, rxref_5aaa19aa-c75c-4978-b731-f3046e84217d.xml, t, x, z"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: rxprocs.h
req.include-header: Rxprocs.h
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
-	rxprocs.h
apiname:
-	RxFinalizeNetFcb
product: Windows
targetos: Windows
req.typenames: RX_CONTEXT, *PRX_CONTEXT
req.product: Windows 10 or later.
---

# RxFinalizeNetFcb function


## -description


<b>RxFinalizeNetFCB</b> finalizes the given FCB structure. The caller must have an exclusive lock on the NET_ROOT associated with FCB. 


## -syntax


````
BOOLEAN RxFinalizeNetFcb(
  _Out_ PFCB    ThisFcb,
  _In_  BOOLEAN RecursiveFinalize,
  _In_  BOOLEAN ForceFinalize,
  _In_  LONG    ReferenceCount
);
````


## -parameters




### -param ThisFcb [out]

A pointer to the FCB structure to finalize.


### -param RecursiveFinalize [in]

The value indicating whether the finalization should be done recursively. 


### -param ForceFinalize [in]

The value indicating whether the finalization should be forced, regardless of the reference count. 

If this parameter is <b>FALSE</b>, then the <b>NodeReferenceCount</b> member of the FCB must be 1 for the FCB to be finalized. 


### -param ReferenceCount [in]

The reference count on the FCB that will still allow forced finalization.


## -returns



<b>RxFinalizeNetFCB</b> returns <b>TRUE</b> on success or <b>FALSE</b> if the finalization did not occur: 




## -remarks



The <b>RxFinalizeNetFCB</b> routine is not normally called by network mini-redirector drivers directly. RDBSS calls this routine internally when an I/O request packet is received for IRP_MJ_CLOSE. This IRP is normally received by RDBSS in response to a user-mode application requesting a file close operation. It is also possible for another kernel driver to issue such an IRP. 

The close handling strategy in RDBSS is predicated upon the axiom that the workload on the server should be minimized as and when possible. There are a number of applications which repeatedly close and open the same file (batch file processing, for example). In these cases the same file is opened, a line from a buffer is read, the file is closed and the same set of operations are repeated over and over again.

This is handled in RDBSS by a delayed processing of the close request. There is a delay of about 10 seconds between completing the request and initiating processing on the close request. This opens up a window during which a subsequent open operation can be collapsed onto an existing SRV_OPEN. The time interval can be tuned to meet these requirements.

Before calling <b>RxFinalizeNetFCB</b>, a lock on the FCB structure must be acquired in exclusive mode. 

If the <i>RecursiveFinalize </i>parameter is <b>FALSE</b>, then <b>RxFinalizeNetFCB</b> will fail if there are outstanding references to the FCB (the <b>OpenCount</b> or <b>CleanCount</b> members of the FCB structureare non zero).

If the <i>ForceFinalize </i>parameter is <b>TRUE</b>, <b>RxFinalizeNetFCB</b> causes the system to ASSERT on checked builds. 

After recursive finalization, the reference count associated with the FCB could be at most 1 for further finalization to occur. This final reference count belongs to the prefix name table of the NET_ROOT. The actual finalization is divided into two parts:

<ul>
<li>
if the reference count equals 1 or the <i>ForceFinalize</i> parameter was <b>TRUE</b>, <b>RxFinalizeNetFCB</b> finalizes the FCB.

</li>
<li>
if the reference count goes to zero, the FCB is finalized and the memory used for the FCB is also released.

</li>
</ul>



## -see-also

<a href="..\fcb\nf-fcb-rxcreatenetfobx.md">RxCreateNetFobx</a>



<a href="..\fcb\nf-fcb-rxcreatenetroot.md">RxCreateNetRoot</a>



<a href="..\fcb\nf-fcb-rxfinishfcbinitialization.md">RxFinishFcbInitialization</a>



<a href="..\fcb\nf-fcb-rxfinalizenetfobx.md">RxFinalizeNetFobx</a>



<a href="..\rxprocs\nf-rxprocs-rxdereference.md">RxDereference</a>



<a href="..\fcb\nf-fcb-rxpreferencenetfcb.md">RxpReferenceNetFcb</a>



<a href="..\fcb\nf-fcb-rxpdereferencenetfcb.md">RxpDereferenceNetFcb</a>



<a href="..\fcb\nf-fcb-rxfinalizesrvopen.md">RxFinalizeSrvOpen</a>



<a href="..\rxprocs\nf-rxprocs-rxreference.md">RxReference</a>



<a href="..\fcb\nf-fcb-rxfinalizevnetroot.md">RxFinalizeVNetRoot</a>



<a href="..\fcb\nf-fcb-rxfinalizesrvcall.md">RxFinalizeSrvCall</a>



<a href="..\fcb\nf-fcb-rxfinalizenetroot.md">RxFinalizeNetRoot</a>



<a href="..\rxprocs\nf-rxprocs-rxfinalizeconnection.md">RxFinalizeConnection</a>



<a href="..\rxprocs\nf-rxprocs-rxforcefinalizeallvnetroots.md">RxForceFinalizeAllVNetRoots</a>



<a href="..\fcb\nf-fcb-rxcreatenetfcb.md">RxCreateNetFcb</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-fcb-structure">The FCB Structure</a>



<a href="..\rxprocs\nf-rxprocs-rxsetsrvcalldomainname.md">RxSetSrvCallDomainName</a>



<a href="..\fcb\nf-fcb-rxcreatevnetroot.md">RxCreateVNetRoot</a>



<a href="..\fcb\nf-fcb-rxcreatesrvopen.md">RxCreateSrvOpen</a>



<a href="..\fcb\nf-fcb-rxcreatesrvcall.md">RxCreateSrvCall</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxFinalizeNetFCB function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

