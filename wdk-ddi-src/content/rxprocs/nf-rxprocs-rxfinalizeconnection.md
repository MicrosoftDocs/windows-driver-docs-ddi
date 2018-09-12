---
UID: NF:rxprocs.RxFinalizeConnection
title: RxFinalizeConnection function
author: windows-driver-content
description: RxFinalizeConnection deletes a connection to a share.
old-location: ifsk\rxfinalizeconnection.htm
tech.root: ifsk
ms.assetid: 3f3e6c56-937e-4a4b-885a-71be2e9513d8
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: RxFinalizeConnection, RxFinalizeConnection function [Installable File System Drivers], ifsk.rxfinalizeconnection, rxprocs/RxFinalizeConnection, rxref_4d5f5633-98fc-4cdc-9803-01ccc06486f5.xml
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
req.lib: 
req.dll: 
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rxprocs.h
api_name:
-	RxFinalizeConnection
product:
- Windows
targetos: Windows
req.typenames: 
---

# RxFinalizeConnection function


## -description


<b>RxFinalizeConnection</b> deletes a connection to a share. Any files open on the connection are closed depending on the level of force specified. The network mini-redirector might choose to keep the transport connection open for performance reasons, unless some option is specified to force a close of connection. 


## -parameters




### -param NetRoot [in, out]

A pointer to the NET_ROOT structure being finalized.


### -param OPTIONAL

<p>A pointer to the V_NET_ROOT structure being finalized.</p>


### -param ForceFilesClosed

<p>The flag that controls the behavior of the <b>RxFinalizeConnection</b> routine. The flag can be one of the following values:</p>
  <p></p>
  <dl>
    <dt>
      <a id="TRUE"></a>
      <a id="true"></a>
      <b>TRUE</b>
    </dt>
    
      <p>
        <b>RxFinalizeConnection</b> succeeds no matter what even if orphan files and IRP_MN_NOTIFY_CHANGE_DIRECTORY requests are open. The option forces these orphan files closed.</p>
    
    <dt>
      <a id="FALSE"></a>
      <a id="false"></a>
      <b>FALSE</b>
    </dt>
    
      <p>
        <b>RxFinalizeConnection</b> fails if files or change notifications are open.</p>
    
    <dt>
      <a id="0xff"></a>
      <a id="0XFF"></a>0xff</dt>
    
      <p>
        <b>RxFinalizeConnection</b> removes the extra reference on the V_NET_ROOT structure due to the add connection request, but otherwise act like <b>FALSE</b>. <b>RxFinalizeConnection</b> fails if files or change notifications are open.</p>
    
  </dl>




#### - Level [in]

The flag that controls the behavior of the <b>RxFinalizeConnection</b> routine. The flag can be one of the following values:





#### TRUE

<b>RxFinalizeConnection</b> succeeds no matter what even if orphan files and IRP_MN_NOTIFY_CHANGE_DIRECTORY requests are open. The option forces these orphan files closed.



#### FALSE

<b>RxFinalizeConnection</b> fails if files or change notifications are open.



#### 0xff

<b>RxFinalizeConnection</b> removes the extra reference on the V_NET_ROOT structure due to the add connection request, but otherwise act like <b>FALSE</b>. <b>RxFinalizeConnection</b> fails if files or change notifications are open.


#### - VNetRoot [in, out, optional]

A pointer to the V_NET_ROOT structure being finalized.


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554356">RxCreateNetFcb</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554358">RxCreateNetFobx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554366">RxCreateNetRoot</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554370">RxCreateSrvCall</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554376">RxCreateSrvOpen</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554380">RxCreateVNetRoot</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554388">RxDereference</a>



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



<a href="https://msdn.microsoft.com/f7846343-9af6-4b7f-9c8d-190abb524946">The NET_ROOT Structure</a>



<a href="https://msdn.microsoft.com/866eba91-13b6-4b15-93de-4f627a635c92">The V_NET_ROOT Structure</a>
 

 

