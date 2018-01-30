---
UID: NF:fcb.RxCreateSrvCall
title: RxCreateSrvCall function
author: windows-driver-content
description: RxCreateSrvCall builds a SRV_CALL structure and inserts the name into the net name table maintained by RDBSS.
old-location: ifsk\rxcreatesrvcall.htm
old-project: ifsk
ms.assetid: 0eda9724-686f-4681-a1f0-92bdc36e695d
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ifsk.rxcreatesrvcall, RxCreateSrvCall, rxref_ff4d3641-1ae5-43f1-9c49-0456d11f69b2.xml, fcb/RxCreateSrvCall, RxCreateSrvCall function [Installable File System Drivers]
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
-	RxCreateSrvCall
product: Windows
targetos: Windows
req.typenames: FA_ENTRY, *PFA_ENTRY
---

# RxCreateSrvCall function


## -description


<b>RxCreateSrvCall</b> builds a SRV_CALL structure and inserts the name into the net name table maintained by RDBSS. 


## -syntax


````
PSRV_CALL RxCreateSrvCall(
  _In_     PRX_CONTEXT       RxContext,
  _In_     PUNICODE_STRING   Name,
  _In_opt_ PUNICODE_STRING   InnerNamePrefix,
  _In_     PRX_CONNECTION_ID RxConnectionId
);
````


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

<a href="..\fcb\nf-fcb-rxfinalizesrvcall.md">RxFinalizeSrvCall</a>

<a href="..\rxprocs\nf-rxprocs-rxfinalizeconnection.md">RxFinalizeConnection</a>

<a href="..\rxprocs\nf-rxprocs-rxforcefinalizeallvnetroots.md">RxForceFinalizeAllVNetRoots</a>

<a href="..\fcb\nf-fcb-rxcreatenetfobx.md">RxCreateNetFobx</a>

<a href="..\fcb\nf-fcb-rxfinalizenetfobx.md">RxFinalizeNetFobx</a>

<a href="..\rxprocs\nf-rxprocs-rxsetsrvcalldomainname.md">RxSetSrvCallDomainName</a>

<a href="https://msdn.microsoft.com/9a3bb194-0289-47f4-a5c8-848d8d82cdd7">The SRV_CALL Structure</a>

<a href="..\fcb\nf-fcb-rxcreatenetroot.md">RxCreateNetRoot</a>

<a href="..\fcb\nf-fcb-rxfinalizevnetroot.md">RxFinalizeVNetRoot</a>

<a href="..\rxprocs\nf-rxprocs-rxdereference.md">RxDereference</a>

<a href="..\fcb\nf-fcb-rxfinalizesrvopen.md">RxFinalizeSrvOpen</a>

<a href="..\rxcontx\ns-rxcontx-_rx_context.md">RX_CONTEXT</a>

<a href="..\rxprocs\nf-rxprocs-rxreference.md">RxReference</a>

<a href="..\fcb\nf-fcb-rxcreatesrvopen.md">RxCreateSrvOpen</a>

<a href="..\rxprocs\nf-rxprocs-rxfinalizenetfcb.md">RxFinalizeNetFcb</a>

<a href="..\fcb\nf-fcb-rxcreatevnetroot.md">RxCreateVNetRoot</a>

<a href="..\fcb\nf-fcb-rxfinishfcbinitialization.md">RxFinishFcbInitialization</a>

<a href="..\fcb\nf-fcb-rxpreferencenetfcb.md">RxpReferenceNetFcb</a>

<a href="..\fcb\nf-fcb-rxfinalizenetroot.md">RxFinalizeNetRoot</a>

<a href="..\fcb\nf-fcb-rxcreatenetfcb.md">RxCreateNetFcb</a>

<a href="..\fcb\nf-fcb-rxpdereferencenetfcb.md">RxpDereferenceNetFcb</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxCreateSrvCall function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

