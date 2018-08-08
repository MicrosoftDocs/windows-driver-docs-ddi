---
UID: NF:fcb.RxCreateSrvCall
title: RxCreateSrvCall function
author: windows-driver-content
description: RxCreateSrvCall builds a SRV_CALL structure and inserts the name into the net name table maintained by RDBSS.
old-location: ifsk\rxcreatesrvcall.htm
tech.root: ifsk
ms.assetid: 0eda9724-686f-4681-a1f0-92bdc36e695d
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: RxCreateSrvCall, RxCreateSrvCall function [Installable File System Drivers], fcb/RxCreateSrvCall, ifsk.rxcreatesrvcall, rxref_ff4d3641-1ae5-43f1-9c49-0456d11f69b2.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fcb.h
req.include-header: Rxcontx.h, Mrxfcb.h, Prefix.h, Fcb.h
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
-	RxCreateSrvCall
product:
- Windows
targetos: Windows
req.typenames: 
---

# RxCreateSrvCall function


## -description


<b>RxCreateSrvCall</b> builds a SRV_CALL structure and inserts the name into the net name table maintained by RDBSS. 


## -parameters




### -param RxContext [in]

A pointer to the RX_CONTEXT structure containing the IRP describing a create operation.


### -param Name [in]

A pointer to the name to be inserted in the name table.


### -param OPTIONAL

TBD


### -param RxConnectionId [in]

A pointer to the connection ID to be associated with the name to be inserted in the prefix name table. This parameter can be <b>NULL</b> in which case no connection ID will be associated with the name inserted in the prefix name table.


#### - InnerNamePrefix [in, optional]

A pointer to an optional inner prefix name to be inserted into the name table with the <i>Name</i>.


## -returns



<b>RxCreateSrvCall</b> returns a pointer to a newly created SRV_CALL data structure on success or a <b>NULL</b> pointer on failure. 




## -remarks



The <b>RxCreateSrvCall</b> routine is not normally called by network mini-redirector drivers directly. RDBSS calls this routine internally when an I/O request packet is received for IRP_MJ_CREATE and a SRV_CALL needs to be created. This IRP is normally received by RDBSS in response to a user-mode application requesting a file create operation on a network share. It is also possible for another kernel driver to issue such an IRP. 

Before calling <b>RxCreateSrvCall</b>, a lock on the name table associated with the device object member of the <i>RxContext</i> parameter must be acquired in exclusive mode. 

<b>RxCreateSrvCall</b> initializes the server call parameters passed in through extended attributes as part of the associated RX_CONTEXT structure. Currently this includes initializing the <b>pPrincipalName</b> member of the SRV_CALL which is passed in by the DFS driver. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554751">RX_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554356">RxCreateNetFcb</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554358">RxCreateNetFobx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554366">RxCreateNetRoot</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554376">RxCreateSrvOpen</a>



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



<a href="https://msdn.microsoft.com/9a3bb194-0289-47f4-a5c8-848d8d82cdd7">The SRV_CALL Structure</a>
 

 

