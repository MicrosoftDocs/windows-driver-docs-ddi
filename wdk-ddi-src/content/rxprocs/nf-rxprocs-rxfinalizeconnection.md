---
UID: NF:rxprocs.RxFinalizeConnection
title: RxFinalizeConnection function
author: windows-driver-content
description: RxFinalizeConnection deletes a connection to a share.
old-location: ifsk\rxfinalizeconnection.htm
old-project: ifsk
ms.assetid: 3f3e6c56-937e-4a4b-885a-71be2e9513d8
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: ifsk.rxfinalizeconnection, RxFinalizeConnection function [Installable File System Drivers], rxprocs/RxFinalizeConnection, rxref_4d5f5633-98fc-4cdc-9803-01ccc06486f5.xml, RxFinalizeConnection
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
-	RxFinalizeConnection
product: Windows
targetos: Windows
req.typenames: RX_CONTEXT, *PRX_CONTEXT
req.product: Windows 10 or later.
---

# RxFinalizeConnection function


## -description


<b>RxFinalizeConnection</b> deletes a connection to a share. Any files open on the connection are closed depending on the level of force specified. The network mini-redirector might choose to keep the transport connection open for performance reasons, unless some option is specified to force a close of connection. 


## -syntax


````
NTSTATUS RxFinalizeConnection(
  _Inout_     PNET_ROOT   NetRoot,
  _Inout_opt_ PV_NET_ROOT VNetRoot,
  _In_        LOGICAL     Level
);
````


## -parameters




### -param NetRoot [in, out]

A pointer to the NET_ROOT structure being finalized.


### -param OPTIONAL

TBD


### -param ForceFilesClosed

TBD




#### - VNetRoot [in, out, optional]

A pointer to the V_NET_ROOT structure being finalized.


#### - Level [in]

The flag that controls the behavior of the <b>RxFinalizeConnection</b> routine. The flag can be one of the following values:





#### TRUE

<b>RxFinalizeConnection</b> succeeds no matter what even if orphan files and IRP_MN_NOTIFY_CHANGE_DIRECTORY requests are open. The option forces these orphan files closed.



#### FALSE

<b>RxFinalizeConnection</b> fails if files or change notifications are open.



#### 0xff

<b>RxFinalizeConnection</b> removes the extra reference on the V_NET_ROOT structure due to the add connection request, but otherwise act like <b>FALSE</b>. <b>RxFinalizeConnection</b> fails if files or change notifications are open.


## -returns



<b>RxFinalizeConnection</b> returns STATUS_SUCCESS on success or one of the following error codes on failure: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_CANCELLED</b></dt>
</dl>
</td>
<td width="60%">
The <b>Flags</b> member of the RX_CONTEXT structure indicates the IRP was canceled.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_CONNECTION_IN_USE</b></dt>
</dl>
</td>
<td width="60%">
The connection is still in use.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FILES_OPEN</b></dt>
</dl>
</td>
<td width="60%">
The file was open, so the remote connection should not be deleted.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_LOCK_NOT_GRANTED</b></dt>
</dl>
</td>
<td width="60%">
An exclusive lock on the associated 

</td>
</tr>
</table>
 




## -remarks



<b>RxFinalizeConnection</b> is normally called by a network mini-redirector driver in response to receiving a custom IOCTL request from user mode. For example, a user might execute from the command line a "NET USE x: /d" to delete a share. This request would be mapped through the network provider DLL provided by the network mini-redirector to a custom IOCTL request sent to the network mini-redirector kernel driver which would call the <b>RxFinalizeConnection</b> routine to delete the connection.

<b>RxFinalizeConnection</b> cancels all the outstanding requests for a given V_NET_ROOT structure. These V_NET_ROOT structures are created and deleted independent of the files that are opened and manipulated on them. Therefore it is imperative that when a delete operation is attempted, all the outstanding requests are canceled.




## -see-also

<a href="https://msdn.microsoft.com/866eba91-13b6-4b15-93de-4f627a635c92">The V_NET_ROOT Structure</a>



<a href="..\fcb\nf-fcb-rxcreatesrvopen.md">RxCreateSrvOpen</a>



<a href="..\fcb\nf-fcb-rxfinalizevnetroot.md">RxFinalizeVNetRoot</a>



<a href="..\fcb\nf-fcb-rxcreatenetfcb.md">RxCreateNetFcb</a>



<a href="..\rxprocs\nf-rxprocs-rxreference.md">RxReference</a>



<a href="..\fcb\nf-fcb-rxfinishfcbinitialization.md">RxFinishFcbInitialization</a>



<a href="..\fcb\nf-fcb-rxfinalizesrvopen.md">RxFinalizeSrvOpen</a>



<a href="..\fcb\nf-fcb-rxcreatevnetroot.md">RxCreateVNetRoot</a>



<a href="..\rxprocs\nf-rxprocs-rxforcefinalizeallvnetroots.md">RxForceFinalizeAllVNetRoots</a>



<a href="..\fcb\nf-fcb-rxcreatesrvcall.md">RxCreateSrvCall</a>



<a href="..\rxprocs\nf-rxprocs-rxsetsrvcalldomainname.md">RxSetSrvCallDomainName</a>



<a href="..\fcb\nf-fcb-rxcreatenetfobx.md">RxCreateNetFobx</a>



<a href="..\fcb\nf-fcb-rxfinalizesrvcall.md">RxFinalizeSrvCall</a>



<a href="..\fcb\nf-fcb-rxcreatenetroot.md">RxCreateNetRoot</a>



<a href="..\rxprocs\nf-rxprocs-rxdereference.md">RxDereference</a>



<a href="https://msdn.microsoft.com/f7846343-9af6-4b7f-9c8d-190abb524946">The NET_ROOT Structure</a>



<a href="..\rxprocs\nf-rxprocs-rxfinalizenetfcb.md">RxFinalizeNetFcb</a>



<a href="..\fcb\nf-fcb-rxfinalizenetroot.md">RxFinalizeNetRoot</a>



<a href="..\fcb\nf-fcb-rxpdereferencenetfcb.md">RxpDereferenceNetFcb</a>



<a href="..\fcb\nf-fcb-rxpreferencenetfcb.md">RxpReferenceNetFcb</a>



<a href="..\fcb\nf-fcb-rxfinalizenetfobx.md">RxFinalizeNetFobx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxFinalizeConnection function%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

