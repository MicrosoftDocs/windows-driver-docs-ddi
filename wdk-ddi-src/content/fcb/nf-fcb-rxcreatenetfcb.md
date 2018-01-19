---
UID: NF:fcb.RxCreateNetFcb
title: RxCreateNetFcb function
author: windows-driver-content
description: RxCreateNetFCB allocates, initializes, and inserts a new FCB structure into the in-memory data structures for a V_NET_ROOT that this FCB is being opened on. The structure allocated has space for a SRV_OPEN and an FOBX structure.
old-location: ifsk\rxcreatenetfcb.htm
old-project: ifsk
ms.assetid: 8be20f25-d72d-4c4d-be05-abb38cdd492d
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: RxCreateNetFcb
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
req.alt-api: RxCreateNetFcb
req.alt-loc: fcb.h
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
req.typenames: FA_ENTRY, *PFA_ENTRY
---

# RxCreateNetFcb function



## -description
<b>RxCreateNetFCB</b> allocates, initializes, and inserts a new FCB structure into the in-memory data structures for a V_NET_ROOT that this FCB is being opened on. The structure allocated has space for a SRV_OPEN and an FOBX structure. 



## -syntax

````
PFCB RxCreateNetFcb(
  _In_ PRX_CONTEXT     RxContext,
  _In_ PIRP            Irp,
  _In_ PV_NET_ROOT     VNetRoot,
  _In_ PUNICODE_STRING Name
);
````


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



When this value is set, the FCB structure was created for a paging file and the FCB structure was allocated from non-paged pool memory.

If the FCB to be created is a not a paging file, <b>RxCreateNetFCB</b> allocates paged pool memory when creating the new FCB data structure. 

Windows does not currently allow having a paging file on a remote machine.

If the <b>Create.Flags</b> member in the RX_CONTEXT has the RX_CONTEXT_CREATE_FLAG_ADDEDBACKSLASH flag on, the <b>FcbState</b> member of the FCB has the FCB_STATE_ADDEDBACKSLASH flag set on. 


## -see-also
<dl>
<dt>
<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-fcb-structure">The FCB Structure</a>
</dt>
<dt>
<a href="..\fcb\nf-fcb-rxcreatenetfobx.md">RxCreateNetFobx</a>
</dt>
<dt>
<a href="..\fcb\nf-fcb-rxcreatenetroot.md">RxCreateNetRoot</a>
</dt>
<dt>
<a href="..\fcb\nf-fcb-rxcreatesrvcall.md">RxCreateSrvCall</a>
</dt>
<dt>
<a href="..\fcb\nf-fcb-rxcreatesrvopen.md">RxCreateSrvOpen</a>
</dt>
<dt>
<a href="..\fcb\nf-fcb-rxcreatevnetroot.md">RxCreateVNetRoot</a>
</dt>
<dt>
<a href="..\rxprocs\nf-rxprocs-rxdereference.md">RxDereference</a>
</dt>
<dt>
<a href="..\rxprocs\nf-rxprocs-rxfinalizeconnection.md">RxFinalizeConnection</a>
</dt>
<dt>
<a href="..\rxprocs\nf-rxprocs-rxfinalizenetfcb.md">RxFinalizeNetFcb</a>
</dt>
<dt>
<a href="..\fcb\nf-fcb-rxfinalizenetfobx.md">RxFinalizeNetFobx</a>
</dt>
<dt>
<a href="..\fcb\nf-fcb-rxfinalizenetroot.md">RxFinalizeNetRoot</a>
</dt>
<dt>
<a href="..\fcb\nf-fcb-rxfinalizesrvcall.md">RxFinalizeSrvCall</a>
</dt>
<dt>
<a href="..\fcb\nf-fcb-rxfinalizesrvopen.md">RxFinalizeSrvOpen</a>
</dt>
<dt>
<a href="..\fcb\nf-fcb-rxfinalizevnetroot.md">RxFinalizeVNetRoot</a>
</dt>
<dt>
<a href="..\fcb\nf-fcb-rxfinishfcbinitialization.md">RxFinishFcbInitialization</a>
</dt>
<dt>
<a href="..\rxprocs\nf-rxprocs-rxforcefinalizeallvnetroots.md">RxForceFinalizeAllVNetRoots</a>
</dt>
<dt>
<a href="..\rxprocs\nf-rxprocs-rxreference.md">RxReference</a>
</dt>
<dt>
<a href="..\rxprocs\nf-rxprocs-rxsetsrvcalldomainname.md">RxSetSrvCallDomainName</a>
</dt>
<dt>
<a href="..\fcb\nf-fcb-rxpdereferencenetfcb.md">RxpDereferenceNetFcb</a>
</dt>
<dt>
<a href="..\fcb\nf-fcb-rxpreferencenetfcb.md">RxpReferenceNetFcb</a>
</dt>
<dt>
<a href="..\rxcontx\ns-rxcontx-_rx_context.md">RX_CONTEXT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/866eba91-13b6-4b15-93de-4f627a635c92">The V_NET_ROOT Structure</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxCreateNetFCB function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

