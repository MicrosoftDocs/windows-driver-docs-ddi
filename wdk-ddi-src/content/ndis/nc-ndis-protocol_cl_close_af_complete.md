---
UID: NC:ndis.PROTOCOL_CL_CLOSE_AF_COMPLETE
title: PROTOCOL_CL_CLOSE_AF_COMPLETE
author: windows-driver-content
description: The ProtocolClCloseAfComplete function is used by connection-oriented NDIS clients.
old-location: netvista\protocolclcloseafcomplete.htm
old-project: netvista
ms.assetid: 7597e124-34e4-4326-98b3-c65dbe90ae6f
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: PROTOCOL_CL_CLOSE_AF_COMPLETE, ProtocolClCloseAfComplete, ProtocolClCloseAfComplete callback function [Network Drivers Starting with Windows Vista], condis_client_ref_27fe2447-59c5-4922-b6be-67911961f0e4.xml, ndis/ProtocolClCloseAfComplete, netvista.protocolclcloseafcomplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    ProtocolClCloseAfComplete   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    ProtocolClCloseAfComplete   (NDIS 5.1)) in Windows XP.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ndis.h
api_name:
-	ProtocolClCloseAfComplete
product:
- Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# PROTOCOL_CL_CLOSE_AF_COMPLETE callback


## -description


The 
  <i>ProtocolClCloseAfComplete</i> function is used by connection-oriented NDIS clients. All
  connection-oriented NDIS clients must have 
  <i>ProtocolClCloseAfComplete</i> functions to complete the asynchronous operations that they initiate with 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff561626">NdisClCloseAddressFamily</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_CL_CLOSE_AF_COMPLETE</b> type.
   For more information, see the following Examples section.</div><div> </div>

## -parameters




### -param Status [in]

Specifies the final status of the client-initiated request to close the address family, which can
     be one of the following:
     





#### NDIS_STATUS_SUCCESS

The address family was closed. The 
       <i>NdisAfHandle</i> that represented the open address family, which the client stored in its 
       <i>ProtocolAfContext</i> area, is now invalid.



#### NDIS_STATUS_FAILURE

Either the AF has associated VC(s) and/or registered SAP(s) that the client must release before
       attempting to close the AF, or the client called 
       <b>NdisClCloseAddressFamily</b> twice because NDIS discovered that the AF state was marked as
       "closing."


### -param ProtocolAfContext [in]

Specifies the client-supplied handle to its per-AF context area. The client originally set up this
     context area and passed this handle to NDIS with 
     <b>NdisClOpenAddressFamilyEx</b>.


## -returns



None




## -remarks



After ensuring that it has no outstanding VCs and/or registered SAPs on its open address family, a
    client calls 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561626">NdisClCloseAddressFamily</a> to
    delete the association between itself, a call manager, and a particular underlying NIC. NDIS calls the 
    <i>ProtocolCmCloseAf</i> function for the call manager that this client originally used to open the
    address family as an asynchronous operation. After calling 
    <b>NdisClCloseAddressFamily</b>, the client should consider the 
    <i>NdisAfHandle</i> invalid.

Consequently, the client must have a 
    <i>ProtocolClCloseAfComplete</i> function, which NDIS calls when the asynchronous close-AF operation is
    done. If the input 
    <i>Status</i> is NDIS_STATUS_SUCCESS, the client can release its per-AF context area.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolClCloseAfComplete</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolClCloseAfComplete</i> function that is named "MyClCloseAfComplete", use the <b>PROTOCOL_CL_CLOSE_AF_COMPLETE</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PROTOCOL_CL_CLOSE_AF_COMPLETE MyClCloseAfComplete;</pre>
</td>
</tr>
</table></span></div>
Then, implement your function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID
 MyClCloseAfComplete(
    NDIS_STATUS  Status,
    NDIS_HANDLE  ProtocolAfContext
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>PROTOCOL_CL_CLOSE_AF_COMPLETE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CL_CLOSE_AF_COMPLETE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561626">NdisClCloseAddressFamily</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561639">NdisClOpenAddressFamilyEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562577">NdisFreeMemory</a>



<a href="https://msdn.microsoft.com/2405a405-177a-420a-9628-a340e0d0acb3">
   NdisFreeToNPagedLookasideList</a>



<a href="https://msdn.microsoft.com/a7a02813-62e4-49c5-abb6-a90f4e092b9f">ProtocolCmCloseAf</a>



<a href="https://msdn.microsoft.com/7422c205-bc41-4121-b430-ff9e6b49dc2e">ProtocolCmOpenAf</a>



<a href="https://msdn.microsoft.com/19fa7be2-acb9-42f6-bd9f-5be3e3c8b5fa">ProtocolUnbindAdapterEx</a>
 

 

