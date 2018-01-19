---
UID: NC:ndis.PROTOCOL_CM_DEACTIVATE_VC_COMPLETE
title: PROTOCOL_CM_DEACTIVATE_VC_COMPLETE
author: windows-driver-content
description: The ProtocolCmDeactivateVcComplete function is a required function.
old-location: netvista\protocolcmdeactivatevccomplete.htm
old-project: netvista
ms.assetid: 44ee0e3c-aee9-4e24-9e54-c57248b568b6
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RxNameCacheInitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       ProtocolCmDeactivateVcComplete (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       ProtocolCmDeactivateVcComplete (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ProtocolCmDeactivateVcComplete
req.alt-loc: Ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# PROTOCOL_CM_DEACTIVATE_VC_COMPLETE callback



## -description
The 
  <i>ProtocolCmDeactivateVcComplete</i> function is a required function. 
  <i>ProtocolCmDeactivateVcComplete</i> completes the processing of a call manager-initiated request that the
  underlying miniport driver (and NDIS) deactivate a VC for which 
  <a href="..\ndis\nf-ndis-ndiscmdeactivatevc.md">NdisCmDeactivateVc</a> previously returned
  NDIS_STATUS_PENDING.



## -prototype

````
PROTOCOL_CM_DEACTIVATE_VC_COMPLETE ProtocolCmDeactivateVcComplete;

VOID ProtocolCmDeactivateVcComplete(
  _In_ NDIS_STATUS Status,
  _In_ NDIS_HANDLE CallMgrVcContext
)
{ ... }
````


## -parameters

### -param Status [in]

Specifies the final status of the deactivation.


### -param CallMgrVcContext [in]

Specifies the handle to a call manager-allocated context area in which the call manager maintains
     its per-VC state. The call manager supplied this handle to NDIS from its 
     <a href="..\ndis\nc-ndis-protocol_co_create_vc.md">ProtocolCoCreateVc</a> function.


## -returns
None


## -remarks
NDIS usually calls 
    <i>ProtocolCmDeactivateVcComplete</i> in the context of the call manager's closing down a call on behalf
    of a connection-oriented client. The call manager typically calls 
    <a href="..\ndis\nf-ndis-ndiscmdeactivatevc.md">NdisCmDeactivateVc</a> from its 
    <a href="..\ndis\nc-ndis-protocol_cm_close_call.md">ProtocolCmCloseCall</a> function.
    Whenever 
    <b>NdisCmDeactivateVc</b> returns NDIS_STATUS_PENDING, NDIS subsequently calls its 
    <i>ProtocolCmDeactivateVcComplete</i> function.

That is, when the underlying connection-oriented miniport driver has deactivated the VC, NDIS calls 
    <i>ProtocolCmDeactivateVcComplete</i>. The final status of the deactivation is found in 
    <i>Status</i> . Possible values for the final status include, but are not limited to:



Indicates that the VC was deactivated successfully.

Indicates that an activation is pending on this VC. The call manager should attempt to deactivate
      the VC at a later time.

Indicates that a deactivation is currently pending on this VC. The call manager need not call 
      <b>NdisCmDeactivateVc</b> again as only one call to 
      <b>NdisCmDeactivateVc</b> is required to deactivate a VC.

<i>ProtocolCmDeactivateVcComplete</i> performs whatever postprocessing is necessary to complete the
    deactivation of a virtual connection, such as setting flags in its state area to indicate that the
    connection is inactive or releasing dynamically allocated resources used while the VC is active.

Completion of the deactivation means that all call parameters for the VC used on activation are no
    longer valid. Any further use of the VC is prohibited except to reactivate it with a new set of call
    parameters.

Call managers should release any resources that were allocated for the VC activation and return
    control as quickly as possible. If the call manager previously returned NDIS_STATUS_PENDING from its 
    <a href="..\ndis\nc-ndis-protocol_cm_close_call.md">ProtocolCmCloseCall</a> function and
    all operations to close the call have been completed, 
    <i>ProtocolCmDeactivateVcComplete</i> should now call 
    <b>NdisCmCloseCallComplete</b>.

To define a <i>ProtocolCmDeactivateVcComplete</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolCmDeactivateVcComplete</i> function that is named "MyCmDeactivateVcComplete", use the <b>PROTOCOL_CM_DEACTIVATE_VC_COMPLETE</b> type as shown in this code example:

Then, implement your function as follows:

The <b>PROTOCOL_CM_DEACTIVATE_VC_COMPLETE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CM_DEACTIVATE_VC_COMPLETE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 


## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport_co_deactivate_vc.md">MiniportCoDeactivateVc</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiscmclosecallcomplete.md">NdisCmCloseCallComplete</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiscmdeactivatevc.md">NdisCmDeactivateVc</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cm_close_call.md">ProtocolCmCloseCall</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PROTOCOL_CM_DEACTIVATE_VC_COMPLETE callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

