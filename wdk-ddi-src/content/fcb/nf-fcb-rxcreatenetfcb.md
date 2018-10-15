---
UID: NF:fcb.RxCreateNetFcb
title: RxCreateNetFcb function
author: windows-driver-content
description: RxCreateNetFCB allocates, initializes, and inserts a new FCB structure into the in-memory data structures for a V_NET_ROOT that this FCB is being opened on. The structure allocated has space for a SRV_OPEN and an FOBX structure.
old-location: ifsk\rxcreatenetfcb.htm
tech.root: ifsk
ms.assetid: 8be20f25-d72d-4c4d-be05-abb38cdd492d
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: RxCreateNetFCB, RxCreateNetFcb, RxCreateNetFcb function [Installable File System Drivers], fcb/RxCreateNetFcb, ifsk.rxcreatenetfcb, rxref_d5f0cde4-daba-475d-9a63-b56047cc24e2.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fcb.h
req.include-header: Rxcontx.h, Mrxfcb.h, Fcb.h
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
-	RxCreateNetFcb
product:
- Windows
targetos: Windows
req.typenames: 
---

# RxCreateNetFcb function


## -description


<b>RxCreateNetFCB</b> allocates, initializes, and inserts a new FCB structure into the in-memory data structures for a V_NET_ROOT that this FCB is being opened on. The structure allocated has space for a SRV_OPEN and an FOBX structure. 


## -parameters




### -param RxContext [in]

A pointer to the RX_CONTEXT structure describing a create operation.


### -param Irp [in]

A pointer to the IRP encapsulated by this RX_CONTEXT structure.


### -param VNetRoot [in]

A pointer to the V_NET_ROOT structure that this FCB is being opened on.


### -param Name [in]

The name of the FCB. The V_NET_ROOT may contain a name prefix that is to be prepended here.


## -returns



<b>RxCreateNetFCB</b> returns a pointer to a newly allocated FCB data structure on success or a <b>NULL</b> pointer on failure. 




## -remarks



The <b>RxCreateNetFCB</b> routine is not normally called by network mini-redirector drivers directly. RDBSS calls this routine internally when an I/O request packet is received for IRP_MJ_CREATE and an FCB structure needs to be created. This IRP is normally received by RDBSS in response to a user-mode application requesting a file create operation on a network share. It is also possible for another kernel driver to issue such an IRP. 

If the FCB to be created is a paging file, <b>RxCreateNetFCB</b> allocates non-paged pool memory when creating the new FCB data structure and sets the following flag on in the FcbState member of the FCB:



If the FCB to be created is a not a paging file, <b>RxCreateNetFCB</b> allocates paged pool memory when creating the new FCB data structure. 

Windows does not currently allow having a paging file on a remote machine.

If the <b>Create.Flags</b> member in the RX_CONTEXT has the RX_CONTEXT_CREATE_FLAG_ADDEDBACKSLASH flag on, the <b>FcbState</b> member of the FCB has the FCB_STATE_ADDEDBACKSLASH flag set on. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554751">RX_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554358">RxCreateNetFobx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554366">RxCreateNetRoot</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554370">RxCreateSrvCall</a>



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



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/the-fcb-structure">The FCB Structure</a>



<a href="https://msdn.microsoft.com/866eba91-13b6-4b15-93de-4f627a635c92">The V_NET_ROOT Structure</a>
 

 

