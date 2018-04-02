---
UID: NC:ndis.PROTOCOL_CL_OPEN_AF_COMPLETE_EX
title: PROTOCOL_CL_OPEN_AF_COMPLETE_EX
author: windows-driver-content
description: The ProtocolClOpenAfCompleteEx function completes the opening of an address family (AF) that was started when a CoNDIS client called the NdisClOpenAddressFamilyEx function.Note  You must declare the function by using the PROTOCOL_CL_OPEN_AF_COMPLETE_EX type. For more information, see the following Examples section.
old-location: netvista\protocolclopenafcompleteex.htm
old-project: netvista
ms.assetid: 03ddbbfd-8fe8-44b6-8d3e-12a7bf6f8f6b
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: PROTOCOL_CL_OPEN_AF_COMPLETE_EX, ProtocolClOpenAfCompleteEx, ProtocolClOpenAfCompleteEx callback function [Network Drivers Starting with Windows Vista], condis_client_ref_8b7e876e-d2b2-4676-8120-aa18f717cca2.xml, ndis/ProtocolClOpenAfCompleteEx, netvista.protocolclopenafcompleteex
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ndis.h
api_name:
-	ProtocolClOpenAfCompleteEx
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# PROTOCOL_CL_OPEN_AF_COMPLETE_EX callback


## -description


The 
  <i>ProtocolClOpenAfCompleteEx</i> function completes the opening of an address family (AF) that was started
  when a CoNDIS client called the 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff561639">NdisClOpenAddressFamilyEx</a> function.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>PROTOCOL_CL_OPEN_AF_COMPLETE_EX</b> type.
   For more information, see the following Examples section.</div><div> </div>

## -parameters




### -param ProtocolAfContext [in]

A client-supplied handle to its context area for an address AF. The client allocated this context
     area and passed this handle to NDIS in its call to the 
     <a href="https://msdn.microsoft.com/54170917-60b4-4d8f-bf92-df7d7dc0faee">
     NdisClOpenAddressFamilyEx</a> function.


### -param NdisAfHandle [in]

An NDIS-supplied handle to an AF, if 
     <i>Status</i> is NDIS_STATUS_SUCCESS. Otherwise, this parameter is <b>NULL</b>. This handle represents an
     association that NDIS established between the client and a call manager that is bound to a CoNDIS
     miniport adapter. If the handle is not <b>NULL</b>, the client must save the handle for use in subsequent calls
     to 
     <b>NdisCl<i>Xxx</i></b> and 
     <b>NdisCo<i>Xxx</i></b> functions.


### -param Status [in]

The final status of the client's call to 
     <b>NdisClOpenAddressFamilyEx</b>, which can be any of the following: 
     





#### NDIS_STATUS_SUCCESS

The AF has been opened, so the client can initialize its state at 
       <i>ProtocolAfContext</i> and use the returned handle from 
       <i>NdisAfHandle</i> in subsequent calls to 
       <b>NdisCl<i>Xxx</i></b> and 
       <b>NdisCo<i>Xxx</i></b> functions, such as 
       <a href="https://msdn.microsoft.com/library/windows/hardware/ff561711">NdisCoOidRequest</a>.



#### NDIS_STATUS_RESOURCES

The requested operation failed because NDIS or the call manager could not allocate sufficient
       memory or initialize the state that one of them uses to track the client's open of the AF that 
       <i>ProtocolAfContext</i> specifies.



#### NDIS_STATUS_FAILURE

NDIS failed the call, possibly for one of the following reasons:
       

<ul>
<li>
The given AF does not match any AF that was registered for the underlying miniport driver to
         which the caller is bound.

</li>
<li>
The caller's adapter binding is closing.

</li>
<li>
The call manager that registered the specified AF is closing its binding to the underlying
         miniport adapter.

</li>
</ul>

## -returns



None




## -remarks



The 
    <i>ProtocolClOpenAfCompleteEx</i> function is required for CoNDIS clients. CoNDIS clients must provide 
    <i>ProtocolClOpenAfCompleteEx</i> to complete the asynchronous operations that the clients initiate by
    calling the 
    <a href="https://msdn.microsoft.com/54170917-60b4-4d8f-bf92-df7d7dc0faee">
    NdisClOpenAddressFamilyEx</a> function.

NDIS calls 
    <i>ProtocolClOpenAfCompleteEx</i> to indicate that some or all of the following have occurred:

<ul>
<li>
If all of the parameters that the client's 
      <a href="https://msdn.microsoft.com/272d99da-ef08-4ebd-90e7-74e99410b3f5">
      ProtocolCoAfRegisterNotify</a> function passed to the 
      <b>NdisClOpenAddressFamilyEx</b> function were valid, NDIS called the 
      <a href="https://msdn.microsoft.com/7422c205-bc41-4121-b430-ff9e6b49dc2e">ProtocolCmOpenAf</a> function of the
      call manager that just registered the specified AF with NDIS.

</li>
<li>
The call manager has examined the specification that the client's 
      <i>ProtocolCoAfRegisterNotify</i> function passed to 
      <b>NdisClOpenAddressFamilyEx</b> at the 
      <i>AddressFamily</i> parameter and returned whether it was valid for this call manager to NDIS.

</li>
</ul>
If the client's attempt to open an AF fails, NDIS cleans up its saved state before calling 
    <i>ProtocolClOpenAfCompleteEx</i>. In this case, 
    <i>ProtocolClOpenAfCompleteEx</i> can release the resources that the client allocated for its call to 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561639">NdisClOpenAddressFamilyEx</a> or
    prepare them for reuse.

Otherwise, 
    <i>ProtocolClOpenAfCompleteEx</i> should set up whatever client-determined state the client will need for
    subsequent operations on the newly opened AF. In particular, the client must save the handle from the 
    <i>NdisAfHandle</i> parameter, typically in the client's 
    <i>ProtocolAfContext</i> context area.

If the client accepts incoming calls, it might allocate a per-service access point (SAP) state area
    and call the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561648">NdisClRegisterSap</a> function. If the
    client makes outgoing calls, it might allocate a per-virtual connection (VC) state area and create a VC
    with the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561696">NdisCoCreateVc</a> function to prepare for an
    incoming request from one of the client's own clients to make an outgoing call to a remote node.

NDIS calls 
    <i>ProtocolClOpenAfCompleteEx</i> at IRQL = PASSIVE_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>ProtocolClOpenAfCompleteEx</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolClOpenAfCompleteEx</i> function that is named "MyClOpenAfCompleteEx", use the <b>PROTOCOL_CL_OPEN_AF_COMPLETE_EX</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PROTOCOL_CL_OPEN_AF_COMPLETE_EX MyClOpenAfCompleteEx;</pre>
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
 MyClOpenAfCompleteEx(
    NDIS_HANDLE  ProtocolAfContext,
    NDIS_HANDLE  NdisAfHandle,
    NDIS_STATUS  Status
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>PROTOCOL_CL_OPEN_AF_COMPLETE_EX</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CL_OPEN_AF_COMPLETE_EX</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561639">NdisClOpenAddressFamilyEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561648">NdisClRegisterSap</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561696">NdisCoCreateVc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561711">NdisCoOidRequest</a>



<a href="https://msdn.microsoft.com/7422c205-bc41-4121-b430-ff9e6b49dc2e">ProtocolCmOpenAf</a>



<a href="https://msdn.microsoft.com/272d99da-ef08-4ebd-90e7-74e99410b3f5">ProtocolCoAfRegisterNotify</a>
 

 

