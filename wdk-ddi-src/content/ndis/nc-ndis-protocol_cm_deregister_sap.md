---
UID: NC:ndis.PROTOCOL_CM_DEREGISTER_SAP
title: PROTOCOL_CM_DEREGISTER_SAP
author: windows-driver-content
description: The ProtocolCmDeregisterSap function is required.
old-location: netvista\protocolcmderegistersap.htm
old-project: netvista
ms.assetid: 738c426e-aa4f-4f59-b955-fbf67071303f
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RxNameCacheInitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    ProtocolCmDeregisterSap (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    ProtocolCmDeregisterSap (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ProtocolCmDeregisterSap
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

# PROTOCOL_CM_DEREGISTER_SAP callback



## -description
The 
  <i>ProtocolCmDeregisterSap</i> function is required. This function is called by NDIS to request that a call
  manager deregister a SAP on behalf of a connection-oriented client.



## -prototype

````
PROTOCOL_CM_DEREGISTER_SAP ProtocolCmDeregisterSap;

NDIS_STATUS ProtocolCmDeregisterSap(
  _In_ NDIS_HANDLE CallMgrSapContext
)
{ ... }
````


## -parameters

### -param CallMgrSapContext [in]

Specifies the handle to a call manager-allocated context area in which the call manager maintains
     its per-SAP state information. The call manager supplied this handle to NDIS from its 
     <a href="..\ndis\nc-ndis-protocol_cm_reg_sap.md">
     ProtocolCmRegisterSap</a> function.


## -returns
<i>ProtocolCmDeregisterSap</i> returns the status of its operation(s) as one of the following:
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>Indicates that the call manager successfully removed the SAP registration and freed any
       resources allocated to maintain per-SAP information.
<dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl>Indicates that the call manager will complete the request to deregister the SAP asynchronously.
       The call manager must call 
       <a href="..\ndis\nf-ndis-ndiscmderegistersapcomplete.md">
       NdisCmDeregisterSapComplete</a> to signal NDIS when the operation is complete.

 


## -remarks
<i>ProtocolCmDeregisterSap</i> communicates with network control devices or other media-specific agents,
    as necessary, to deregister the SAP on the network. Such actions could include, but are not limited
    to:

Communicating with a switching hardware

Communicating with a network control station

Communicating with other media-specific network agents

If a call manager is required to communicate with networking control agents, such as a network switch,
    it should use a virtual connection to the network control agent that it established in its 
    <a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a> function.
    Stand-alone call managers communicate through the underlying miniport driver by calling 
    <a href="..\ndis\nf-ndis-ndiscosendnetbufferlists.md">NdisCoSendNetBufferLists</a>.
    Miniport drivers that provide integrated call-management support never call 
    <b>NdisCoSendNetBufferLists</b>. Instead, they transmit the data directly across the network.

In addition, 
    <i>ProtocolCmDeregisterSap</i> must free any dynamically-allocated resources in its per-SAP area, provided
    at 
    <i>CallMgrSapContext</i>, as well as freeing the state area itself before returning control to NDIS.

To define a <i>ProtocolCmDeregisterSap</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolCmDeregisterSap</i> function that is named "MyCmDeregisterSap", use the <b>PROTOCOL_CM_DEREGISTER_SAP</b> type as shown in this code example:

Then, implement your function as follows:

The <b>PROTOCOL_CM_DEREGISTER_SAP</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CM_DEREGISTER_SAP</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 


## -see-also
<dl>
<dt>
<a href="..\ndis\nf-ndis-ndiscmderegistersapcomplete.md">NdisCmDeregisterSapComplete</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiscosendnetbufferlists.md">NdisCoSendNetBufferLists</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cm_reg_sap.md">ProtocolCmRegisterSap</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PROTOCOL_CM_DEREGISTER_SAP callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

