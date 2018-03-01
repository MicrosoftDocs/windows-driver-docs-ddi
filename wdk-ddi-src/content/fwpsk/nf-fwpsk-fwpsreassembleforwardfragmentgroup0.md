---
UID: NF:fwpsk.FwpsReassembleForwardFragmentGroup0
title: FwpsReassembleForwardFragmentGroup0 function
author: windows-driver-content
description: The FwpsReassembleForwardFragmentGroup0 function assembles a list of IP fragments in the forwarding data path into a single packet.Note  FwpsReassembleForwardFragmentGroup0 is a specific version of FwpsReassembleForwardFragmentGroup.
old-location: netvista\fwpsreassembleforwardfragmentgroup0.htm
old-project: netvista
ms.assetid: 00322dbf-0099-439a-8d65-bf530129cea1
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FwpsReassembleForwardFragmentGroup0, FwpsReassembleForwardFragmentGroup0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsReassembleForwardFragmentGroup0, netvista.fwpsreassembleforwardfragmentgroup0, wfp_ref_2_funct_3_fwps_R-Z_354e1536-de02-474d-b99f-b5d81875aecd.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Server 2008.
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
req.lib: Fwpkclnt.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	fwpkclnt.lib
-	fwpkclnt.dll
api_name:
-	FwpsReassembleForwardFragmentGroup0
product: Windows
targetos: Windows
req.typenames: FWPS_VSWITCH_EVENT_TYPE
---

# FwpsReassembleForwardFragmentGroup0 function


## -description


The 
  <b>FwpsReassembleForwardFragmentGroup0</b> function assembles a list of IP fragments in the forwarding data
  path into a single packet.
<div class="alert"><b>Note</b>  <b>FwpsReassembleForwardFragmentGroup0</b> is a specific version of <b>FwpsReassembleForwardFragmentGroup</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -syntax


````
NTSTATUS NTAPI FwpsReassembleForwardFragmentGroup0(
  _In_     ADDRESS_FAMILY  addressFamily,
  _Inout_  NET_BUFFER_LIST *fragmentGroupNblChain,
  _In_opt_ NDIS_HANDLE     netBufferAndNetBufferListPoolHandle,
  _In_     ULONG           dataBackFill,
  _In_     ULONG           flags,
  _Out_    NET_BUFFER_LIST **reassembledNbl
);
````


## -parameters




### -param addressFamily [in]

One of the following address families:
     





#### AF_INET

The IPv4 address family.



#### AF_INET6

The IPv6 address family.


### -param fragmentGroupNblChain [in, out]

A pointer to the 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> chain of IP fragments to
     reassemble into a single packet. For more information on the usage of
     this parameter, see Remarks.


### -param netBufferAndNetBufferListPoolHandle [in, optional]

An optional 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure pool handle that
     was previously returned from the 
     <a href="..\ndis\nf-ndis-ndisallocatenetbufferlistpool.md">
     NdisAllocateNetBufferListPool</a> function. The 
     <b>fAllocateNetBuffer</b> member of the 
     <a href="..\ndis\ns-ndis-_net_buffer_list_pool_parameters.md">NET_BUFFER_LIST_POOL_PARAMETERS</a> structure that the caller passed to 
     <b>NdisAllocateNetBufferListPool</b> must have been set to <b>TRUE</b>, and the 
     <b>DataSize</b> member set to zero. If this parameter is <b>NULL</b>, NDIS uses an internal pool.


### -param dataBackFill [in]

If allocation of 
     unused data space (backfill space) is required, this parameter specifies the number of bytes of
     unused data space to allocate.


### -param flags [in]

Reserved. Callout drivers must set this parameter to zero.


### -param reassembledNbl [out]

A pointer to a 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> pointer that receives the
     address of the reassembled single network buffer list.


## -returns



The 
     <b>FwpsReassembleForwardFragmentGroup0</b> function returns one of the following NTSTATUS codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The list of IP fragments was successfully reassembled into a single 
       <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FWP_TCPIP_NOT_READY</b></dt>
</dl>
</td>
<td width="60%">
The TCP/IP network stack is not ready to perform packet reassembly. This error can occur if this
       function is called before 
       Tcpip.sys is loaded, or after 
       Tcpip.sys has been unloaded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
An error occurred.

</td>
</tr>
</table>
 




## -remarks



The 
    <b>FwpsReassembleForwardFragmentGroup0</b> function assembles a list of IP fragments in the forwarding
    data path, described by a 
    <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> chain, into a single packet.
    The reassembled packet is a single net buffer list that contains one net buffer and references the input
    fragment chain. This function is typically used by edge firewalls to inspect network packets.

The input chain of IP fragments, 
    <i>fragmentGroupNblChain</i>, must be one that is indicated by the 
    <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a> callout function to the
    FWPS_LAYER_IPFORWARD_V4 or FWPS_LAYER_IPFORWARD_V6 layer when the FWP_CONDITION_FLAG_IS_FRAGMENT_GROUP
    flag is set. If this is not the case, the behavior of 
    <b>FwpsReassembleForwardFragmentGroup0</b> is undefined.

Call the 
    <a href="..\fwpsk\nf-fwpsk-fwpsfreenetbufferlist0.md">FwpsFreeNetBufferList0</a> function to
    free the 
    <i>reassembledNbl</i> NET_BUFFER_LIST structure and all of the associated 
    <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structures and MDL chains. 
    <b>FwpsFreeNetBufferList0</b> dereferences the original input fragment chain.

You can use the following command to view the current "Group Forwarded Fragments" setting for the
    system: 
    <b>netsh interface {ipv4|ipv6} show global</b>.

Because 
    <b>FwpsReassembleForwardFragmentGroup0</b> references the input fragment chain, it is not necessary for
    callouts to reference or clone the chain prior to calling this function.




## -see-also

<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>



<a href="..\ndis\nf-ndis-ndisallocatenetbufferlistpool.md">
   NdisAllocateNetBufferListPool</a>



<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>



<a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a>



<a href="..\fwpsk\nf-fwpsk-fwpsfreenetbufferlist0.md">FwpsFreeNetBufferList0</a>



<a href="..\ndis\ns-ndis-_net_buffer_list_pool_parameters.md">NET_BUFFER_LIST_POOL_PARAMETERS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsReassembleForwardFragmentGroup0 function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

