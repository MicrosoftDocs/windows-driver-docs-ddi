---
UID: NF:rxprocs.RxForceFinalizeAllVNetRoots
title: RxForceFinalizeAllVNetRoots function (rxprocs.h)
description: RxForceFinalizeAllVNetRoots force finalizes all the V_NET_ROOT structures associated with a given NET_ROOT structure. The caller must have an exclusive lock on the netname table associated with the device object.
old-location: ifsk\rxforcefinalizeallvnetroots.htm
tech.root: ifsk
ms.assetid: 39b64fc0-70e6-4bca-ac45-817b27681487
ms.date: 04/16/2018
ms.keywords: RxForceFinalizeAllVNetRoots, RxForceFinalizeAllVNetRoots function [Installable File System Drivers], ifsk.rxforcefinalizeallvnetroots, rxprocs/RxForceFinalizeAllVNetRoots, rxref_4202642f-d7a8-4649-8395-4f2e423ca062.xml
ms.topic: function
f1_keywords:
 - "rxprocs/RxForceFinalizeAllVNetRoots"
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
req.lib: 
req.dll: 
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- rxprocs.h
api_name:
- RxForceFinalizeAllVNetRoots
product:
- Windows
targetos: Windows
req.typenames: 
---

# RxForceFinalizeAllVNetRoots function


## -description


<b>RxForceFinalizeAllVNetRoots</b> force finalizes all the V_NET_ROOT structures associated with a given NET_ROOT structure. The caller must have an exclusive lock on the netname table associated with the device object. 


## -parameters




### -param NetRoot

A pointer to the NET_ROOT structure.


## -remarks



The <b>RxForceFinalizeAllVNetRoots</b> routine is not called internally by RDBSS. <b>RxForceFinalizeAllVNetRoots</b> is normally called by network mini-redirector drivers directly. If a network mini-redirector implements client-side caching, the <b>RxForceFinalizeAllVNetRoots</b> routine could be used to close all open files for client-side caching. Forcing a close on all the V_NET_ROOT structures is equivalent to a <a href="https://docs.microsoft.com/windows/desktop/api/winnetwk/nf-winnetwk-wnetcancelconnectiona">WNetCancelConnection</a> call from user mode on a share with forced close of all files.

Before calling <b>RxForceFinalizeAllVNetRoots</b>, a lock on the netname table associated with the device object must be acquired in exclusive mode. 

<b>RxForceFinalizeAllVNetRoots</b> calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxfinalizevnetroot">RxFinalizeVNetRoot</a> to finalize each V_NET_ROOT associated with the NET_ROOT.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxcreatenetfcb">RxCreateNetFcb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxcreatenetfobx">RxCreateNetFobx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxcreatenetroot">RxCreateNetRoot</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxcreatesrvcall">RxCreateSrvCall</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxcreatesrvopen">RxCreateSrvOpen</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxcreatevnetroot">RxCreateVNetRoot</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxdereference">RxDereference</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxfinalizeconnection">RxFinalizeConnection</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxfinalizenetfcb">RxFinalizeNetFcb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxfinalizenetfobx">RxFinalizeNetFobx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxfinalizenetroot">RxFinalizeNetRoot</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxfinalizesrvcall">RxFinalizeSrvCall</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxfinalizesrvopen">RxFinalizeSrvOpen</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxfinalizevnetroot">RxFinalizeVNetRoot</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxfinishfcbinitialization">RxFinishFcbInitialization</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxreference">RxReference</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/rxprocs/nf-rxprocs-rxsetsrvcalldomainname">RxSetSrvCallDomainName</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxpdereferencenetfcb">RxpDereferenceNetFcb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fcb/nf-fcb-rxpreferencenetfcb">RxpReferenceNetFcb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/the-net-root-structure">The NET_ROOT Structure</a>
 

 

