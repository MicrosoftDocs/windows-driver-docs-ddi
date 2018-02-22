---
UID: NF:rxprocs.RxForceFinalizeAllVNetRoots
title: RxForceFinalizeAllVNetRoots function
author: windows-driver-content
description: RxForceFinalizeAllVNetRoots force finalizes all the V_NET_ROOT structures associated with a given NET_ROOT structure. The caller must have an exclusive lock on the netname table associated with the device object.
old-location: ifsk\rxforcefinalizeallvnetroots.htm
old-project: ifsk
ms.assetid: 39b64fc0-70e6-4bca-ac45-817b27681487
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: rxprocs/RxForceFinalizeAllVNetRoots, rxref_4202642f-d7a8-4649-8395-4f2e423ca062.xml, RxForceFinalizeAllVNetRoots, ifsk.rxforcefinalizeallvnetroots, RxForceFinalizeAllVNetRoots function [Installable File System Drivers]
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
-	RxForceFinalizeAllVNetRoots
product: Windows
targetos: Windows
req.typenames: RX_CONTEXT, *PRX_CONTEXT
req.product: Windows 10 or later.
---

# RxForceFinalizeAllVNetRoots function


## -description


<b>RxForceFinalizeAllVNetRoots</b> force finalizes all the V_NET_ROOT structures associated with a given NET_ROOT structure. The caller must have an exclusive lock on the netname table associated with the device object. 


## -syntax


````
VOID RxForceFinalizeAllVNetRoots(
   PNET_ROOT NetRoot
);
````


## -parameters




### -param NetRoot

A pointer to the NET_ROOT structure.


## -returns



None




## -remarks



The <b>RxForceFinalizeAllVNetRoots</b> routine is not called internally by RDBSS. <b>RxForceFinalizeAllVNetRoots</b> is normally called by network mini-redirector drivers directly. If a network mini-redirector implements client-side caching, the <b>RxForceFinalizeAllVNetRoots</b> routine could be used to close all open files for client-side caching. Forcing a close on all the V_NET_ROOT structures is equivalent to a <a href="https://msdn.microsoft.com/e180d497-5e14-459a-8cf6-5664dfb88419">WNetCancelConnection</a> call from user mode on a share with forced close of all files.

Before calling <b>RxForceFinalizeAllVNetRoots</b>, a lock on the netname table associated with the device object must be acquired in exclusive mode. 

<b>RxForceFinalizeAllVNetRoots</b> calls <a href="..\fcb\nf-fcb-rxfinalizevnetroot.md">RxFinalizeVNetRoot</a> to finalize each V_NET_ROOT associated with the NET_ROOT.




## -see-also

<a href="..\fcb\nf-fcb-rxcreatevnetroot.md">RxCreateVNetRoot</a>



<a href="..\rxprocs\nf-rxprocs-rxfinalizeconnection.md">RxFinalizeConnection</a>



<a href="..\fcb\nf-fcb-rxfinalizesrvcall.md">RxFinalizeSrvCall</a>



<a href="..\fcb\nf-fcb-rxfinalizesrvopen.md">RxFinalizeSrvOpen</a>



<a href="..\fcb\nf-fcb-rxfinalizenetfobx.md">RxFinalizeNetFobx</a>



<a href="..\rxprocs\nf-rxprocs-rxdereference.md">RxDereference</a>



<a href="..\fcb\nf-fcb-rxcreatesrvcall.md">RxCreateSrvCall</a>



<a href="..\fcb\nf-fcb-rxcreatesrvopen.md">RxCreateSrvOpen</a>



<a href="..\rxprocs\nf-rxprocs-rxreference.md">RxReference</a>



<a href="..\fcb\nf-fcb-rxfinalizevnetroot.md">RxFinalizeVNetRoot</a>



<a href="..\fcb\nf-fcb-rxcreatenetroot.md">RxCreateNetRoot</a>



<a href="..\fcb\nf-fcb-rxfinalizenetroot.md">RxFinalizeNetRoot</a>



<a href="https://msdn.microsoft.com/f7846343-9af6-4b7f-9c8d-190abb524946">The NET_ROOT Structure</a>



<a href="..\fcb\nf-fcb-rxcreatenetfobx.md">RxCreateNetFobx</a>



<a href="..\rxprocs\nf-rxprocs-rxfinalizenetfcb.md">RxFinalizeNetFcb</a>



<a href="..\fcb\nf-fcb-rxpreferencenetfcb.md">RxpReferenceNetFcb</a>



<a href="..\fcb\nf-fcb-rxcreatenetfcb.md">RxCreateNetFcb</a>



<a href="..\fcb\nf-fcb-rxpdereferencenetfcb.md">RxpDereferenceNetFcb</a>



<a href="..\fcb\nf-fcb-rxfinishfcbinitialization.md">RxFinishFcbInitialization</a>



<a href="..\rxprocs\nf-rxprocs-rxsetsrvcalldomainname.md">RxSetSrvCallDomainName</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxForceFinalizeAllVNetRoots function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

