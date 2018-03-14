---
UID: NF:fcb.RxCreateNetRoot
title: RxCreateNetRoot function
author: windows-driver-content
description: RxCreateNetRoot allocates and initializes a NET_ROOT structure and inserts the name into the net name table on the associated device object.
old-location: ifsk\rxcreatenetroot.htm
old-project: ifsk
ms.assetid: 076624d3-96f5-4e93-8598-b880a6b2289b
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RxCreateNetRoot, RxCreateNetRoot function [Installable File System Drivers], fcb/RxCreateNetRoot, ifsk.rxcreatenetroot, rxref_3171aa4b-bf5b-4114-a5a0-40af765b09da.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fcb.h
req.include-header: Rxcontx.h, Mrxfcb.h, Prefix.h, Struchdr.h, Fcb.h
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
-	RxCreateNetRoot
product: Windows
targetos: Windows
req.typenames: FA_ENTRY, *PFA_ENTRY
---

# RxCreateNetRoot function


## -description


<b>RxCreateNetRoot</b> allocates and initializes a NET_ROOT structure and inserts the name into the net name table on the associated device object. 


## -syntax


````
PNET_ROOT RxCreateNetRoot(
  _In_     PSRV_CALL         SrvCall,
  _In_     PUNICODE_STRING   Name,
  _In_     ULONG             NetRootFlags,
  _In_opt_ PRX_CONNECTION_ID RxConnectionId
);
````


## -parameters




### -param SrvCall [in]

A pointer to the associated SRV_CALL structure.


### -param Name [in]

A pointer to the name to be inserted in the name table.


### -param NetRootFlags [in]

The value to set the <b>Flags</b> member of the NET_ROOT which is used to denote the state of the NET_ROOT structure.


### -param RxConnectionId [in, optional]

A pointer to the connection ID to be associated with the name to be inserted in the prefix name table. This parameter can be <b>NULL</b> in which case no connection ID will be associated with the name inserted in the prefix name table.


## -returns



<b>RxCreateNetRoot</b> returns a pointer to a newly created NET_ROOT data structure on success or a <b>NULL</b> pointer on failure. 




## -remarks



The <b>RxCreateNetRoot</b> routine is not normally called by network mini-redirector drivers directly. RDBSS calls this routine internally when an I/O request packet is received for IRP_MJ_CREATE and a NET_ROOT needs to be created. This IRP is normally received by RDBSS in response to a user-mode application requesting a file create operation on a network share. It is also possible for another kernel driver to issue such an IRP. 

Before calling <b>RxCreateNetRoot</b>, a lock on the name table associated with the device object member of the <i>SrvCall</i> parameter must be acquired in exclusive mode. 

The NET_ROOT flags are split into two groups, those visible to network mini redirectors and those invisible to network mini redirectors. The visible ones are the lower 16-bits of the <b>Flags</b> member of the NET_ROOT. This routine does not check or test which flags are being set. 

On success, the reference count for the SRV_CALL structure is incremented. 




## -see-also

<a href="..\fcb\nf-fcb-rxcreatenetfobx.md">RxCreateNetFobx</a>



<a href="..\rxprocs\nf-rxprocs-rxsetsrvcalldomainname.md">RxSetSrvCallDomainName</a>



<a href="..\fcb\nf-fcb-rxfinishfcbinitialization.md">RxFinishFcbInitialization</a>



<a href="..\fcb\nf-fcb-rxfinalizenetfobx.md">RxFinalizeNetFobx</a>



<a href="..\fcb\nf-fcb-rxpreferencenetfcb.md">RxpReferenceNetFcb</a>



<a href="..\rxprocs\nf-rxprocs-rxdereference.md">RxDereference</a>



<a href="..\fcb\nf-fcb-rxcreatevnetroot.md">RxCreateVNetRoot</a>



<a href="..\fcb\nf-fcb-rxcreatesrvcall.md">RxCreateSrvCall</a>



<a href="https://msdn.microsoft.com/9a3bb194-0289-47f4-a5c8-848d8d82cdd7">The SRV_CALL Structure</a>



<a href="..\rxprocs\nf-rxprocs-rxforcefinalizeallvnetroots.md">RxForceFinalizeAllVNetRoots</a>



<a href="..\rxprocs\nf-rxprocs-rxfinalizenetfcb.md">RxFinalizeNetFcb</a>



<a href="..\fcb\nf-fcb-rxcreatesrvopen.md">RxCreateSrvOpen</a>



<a href="..\fcb\nf-fcb-rxcreatenetfcb.md">RxCreateNetFcb</a>



<a href="..\fcb\nf-fcb-rxpdereferencenetfcb.md">RxpDereferenceNetFcb</a>



<a href="..\fcb\nf-fcb-rxfinalizesrvopen.md">RxFinalizeSrvOpen</a>



<a href="..\rxprocs\nf-rxprocs-rxfinalizeconnection.md">RxFinalizeConnection</a>



<a href="..\fcb\nf-fcb-rxfinalizenetroot.md">RxFinalizeNetRoot</a>



<a href="..\fcb\nf-fcb-rxfinalizesrvcall.md">RxFinalizeSrvCall</a>



<a href="https://msdn.microsoft.com/f7846343-9af6-4b7f-9c8d-190abb524946">The NET_ROOT Structure</a>



<a href="..\rxprocs\nf-rxprocs-rxreference.md">RxReference</a>



<a href="..\fcb\nf-fcb-rxfinalizevnetroot.md">RxFinalizeVNetRoot</a>



 

 


