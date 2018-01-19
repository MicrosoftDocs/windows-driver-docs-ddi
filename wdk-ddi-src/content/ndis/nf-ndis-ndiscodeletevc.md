---
UID: NF:ndis.NdisCoDeleteVc
title: NdisCoDeleteVc function
author: windows-driver-content
description: NdisCoDeleteVc destroys a caller-created VC.
old-location: netvista\ndiscodeletevc.htm
old-project: netvista
ms.assetid: 31e88a5b-d97c-482a-aab0-dd987b15d657
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: NdisCoDeleteVc
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisCoDeleteVc (NDIS 5.1)) in   Windows Vista. Supported for NDIS 5.1 drivers (see    NdisCoDeleteVc (NDIS 5.1)) in   Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisCoDeleteVc
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_Connection_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisCoDeleteVc function



## -description
<b>NdisCoDeleteVc</b> destroys a caller-created VC.



## -syntax

````
NDIS_STATUS NdisCoDeleteVc(
  _In_ NDIS_HANDLE NdisVcHandle
);
````


## -parameters

### -param NdisVcHandle [in]

Specifies the handle identifying the VC to be deleted. The caller originally obtained this handle
     from 
     <a href="..\ndis\nf-ndis-ndiscocreatevc.md">NdisCoCreateVc</a>.


## -returns
<b>NdisCoDeleteVc</b> can return one of the following:
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>NDIS deleted the VC.
<dl>
<dt><b>NDIS_STATUS_NOT_ACCEPTED</b></dt>
</dl>The VC is still active, so it could not be deleted.
<dl>
<dt><b>NDIS_STATUS_CLOSING</b></dt>
</dl>This call is redundant, but deactivation on the given VC is still pending.

 


## -remarks
When a protocol calls 
    <b>NdisCoDeleteVc</b>, there must be no outstanding calls on the given VC and that VC already has been
    deactivated. To meet these requirements implies that the following conditions hold:

If the call tear-down was initiated by a local client, that client has already called 
      <a href="..\ndis\nf-ndis-ndisclclosecall.md">NdisClCloseCall</a> with the given 
      <i>NdisVcHandle</i> and its close-call request has completed successfully.

If the call tear-down was initiated by a remote client, the stand-alone call manager has already
      called 
      <a href="..\ndis\nf-ndis-ndiscmdeactivatevc.md">NdisCmDeactivateVc</a> with the given 
      <i>NdisVcHandle</i> and its deactivation request has completed successfully.

Only the protocol that created a particular VC can delete that VC. A call to 
    <b>NdisCoDeleteVc</b> causes NDIS to call both the underlying miniport driver's 
    <a href="..\ndis\nc-ndis-miniport_co_delete_vc.md">MiniportCoDeleteVc</a> function and the 
    <a href="..\ndis\nc-ndis-protocol_co_delete_vc.md">ProtocolCoDeleteVc</a> function of the
    client or call manager with which the caller shares the 
    <i>NdisVcHandle</i> .

When 
    <b>NdisCoDeleteVc</b> returns control, the 
    <i>NdisVcHandle</i> is no longer valid.

Stand-alone call managers, which register themselves with NDIS as protocol drivers, can call 
    <b>NdisCoDeleteVc</b>. Connection-oriented miniport drivers that provide integrated call-management
    support call 
    <a href="..\ndis\nf-ndis-ndismcmdeletevc.md">NdisMCmDeleteVc</a> instead.


## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport_co_delete_vc.md">MiniportCoDeleteVc</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisclclosecall.md">NdisClCloseCall</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiscmdeactivatevc.md">NdisCmDeactivateVc</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiscocreatevc.md">NdisCoCreateVc</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismcmdeletevc.md">NdisMCmDeleteVc</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cl_close_call_complete.md">ProtocolClCloseCallComplete</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cl_incoming_close_call.md">ProtocolClIncomingCloseCall</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cm_close_call.md">ProtocolCmCloseCall</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_co_delete_vc.md">ProtocolCoDeleteVc</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisCoDeleteVc function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

