---
UID: NF:fcb.RxCreateVNetRoot
title: RxCreateVNetRoot function
author: windows-driver-content
description: RxCreateVNetRoot allocates and initializes a NET_ROOT structure and inserts the name into the net name table on the associated device object.
old-location: ifsk\rxcreatevnetroot.htm
old-project: ifsk
ms.assetid: 852cc319-4bcd-427d-802f-3c82c72901f0
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RxCreateVNetRoot, RxCreateVNetRoot function [Installable File System Drivers], fcb/RxCreateVNetRoot, ifsk.rxcreatevnetroot, rxref_adf9e6de-8b07-488e-86de-0d42036c3d7c.xml
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
req.lib: NtosKrnl.exe
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
-	RxCreateVNetRoot
product: Windows
targetos: Windows
req.typenames: FA_ENTRY, *PFA_ENTRY
---

# RxCreateVNetRoot function


## -description


<b>RxCreateVNetRoot</b> allocates and initializes a NET_ROOT structure and inserts the name into the net name table on the associated device object. 


## -syntax


````
PV_NET_ROOT RxCreateVNetRoot(
  _In_ PRX_CONTEXT       RxContext,
  _In_ PNET_ROOT         NetRoot,
  _In_ PUNICODE_STRING   CanonicalName,
  _In_ PUNICODE_STRING   LocalNetRootName,
  _In_ PUNICODE_STRING   FilePath,
  _In_ PRX_CONNECTION_ID RxConnectionId
);
````


## -parameters




### -param RxContext [in]

A pointer to the RDBSS RX_CONTEXT containing the IRP describing a create operation.


### -param NetRoot [in]

A pointer to the associated NET_ROOT structure.


### -param CanonicalName [in]

A pointer to the canonical name to be inserted in the name table.


### -param LocalNetRootName [in]

A pointer to the local NET_ROOT name without the prefix name.


### -param FilePath [in]

A pointer to a file pathname. This parameter is not currently used and can be <b>NULL</b>.


### -param RxConnectionId [in]

A pointer to the connection ID to be associated with the name to be inserted in the prefix name table. This parameter can be <b>NULL</b> in which case no connection ID will be associated with the name inserted in the name table.


## -returns



<b>RxCreateVNetRoot</b> returns a pointer to a newly created V_NET_ROOT data structure on success or a <b>NULL</b> pointer on failure. 




## -remarks



The <b>RxCreateVNetRoot</b> routine is not normally called by network mini-redirector drivers directly. RDBSS calls this routine internally when an I/O request packet is received for IRP_MJ_CREATE and a V_NET_ROOT needs to be created. This IRP is normally received by RDBSS in response to a user-mode application requesting a file create operation on a network share. It is also possible for another kernel driver to issue such an IRP. 

Before calling <b>RxCreateVNetRoot</b>, a lock on the name table associated with the device object member of the <i>RxContext</i> parameter must be acquired in exclusive mode. 

<b>RxCreateVNetRoot</b> sets a variety of security context parameters on the V_NET_ROOT structure based on parameters from the RX_CONTEXT. These parameters include the following: <i>LogonId</i>, <i>SessionId</i>, <i>pUserName</i>, <i>pUserDomainName</i>, <i>pPassword</i>, and <i>Flags</i>. 




## -see-also

<a href="..\rxcontx\ns-rxcontx-_rx_context.md">RX_CONTEXT</a>



<a href="https://msdn.microsoft.com/f7846343-9af6-4b7f-9c8d-190abb524946">The NET_ROOT Structure</a>



<a href="..\rxprocs\nf-rxprocs-rxreference.md">RxReference</a>



<a href="..\fcb\nf-fcb-rxcreatesrvcall.md">RxCreateSrvCall</a>



<a href="https://msdn.microsoft.com/866eba91-13b6-4b15-93de-4f627a635c92">The V_NET_ROOT Structure</a>



<a href="..\fcb\nf-fcb-rxfinalizesrvopen.md">RxFinalizeSrvOpen</a>



<a href="..\fcb\nf-fcb-rxpdereferencenetfcb.md">RxpDereferenceNetFcb</a>



<a href="..\rxprocs\nf-rxprocs-rxforcefinalizeallvnetroots.md">RxForceFinalizeAllVNetRoots</a>



<a href="..\rxprocs\nf-rxprocs-rxdereference.md">RxDereference</a>



<a href="..\fcb\nf-fcb-rxcreatenetroot.md">RxCreateNetRoot</a>



<a href="..\fcb\nf-fcb-rxfinishfcbinitialization.md">RxFinishFcbInitialization</a>



<a href="..\fcb\nf-fcb-rxcreatenetfobx.md">RxCreateNetFobx</a>



<a href="..\fcb\nf-fcb-rxfinalizesrvcall.md">RxFinalizeSrvCall</a>



<a href="..\fcb\nf-fcb-rxfinalizenetfobx.md">RxFinalizeNetFobx</a>



<a href="..\rxprocs\nf-rxprocs-rxfinalizenetfcb.md">RxFinalizeNetFcb</a>



<a href="..\rxprocs\nf-rxprocs-rxsetsrvcalldomainname.md">RxSetSrvCallDomainName</a>



<a href="..\fcb\nf-fcb-rxcreatesrvopen.md">RxCreateSrvOpen</a>



<a href="..\fcb\nf-fcb-rxfinalizevnetroot.md">RxFinalizeVNetRoot</a>



<a href="..\fcb\nf-fcb-rxcreatenetfcb.md">RxCreateNetFcb</a>



<a href="..\fcb\nf-fcb-rxpreferencenetfcb.md">RxpReferenceNetFcb</a>



<a href="..\rxprocs\nf-rxprocs-rxfinalizeconnection.md">RxFinalizeConnection</a>



<a href="..\fcb\nf-fcb-rxinferfiletype.md">RxInferFileType</a>



<a href="..\fcb\nf-fcb-rxfinalizenetroot.md">RxFinalizeNetRoot</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxCreateVNetRoot function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

