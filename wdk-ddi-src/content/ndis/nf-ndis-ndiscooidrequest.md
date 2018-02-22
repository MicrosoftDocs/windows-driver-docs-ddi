---
UID: NF:ndis.NdisCoOidRequest
title: NdisCoOidRequest function
author: windows-driver-content
description: The NdisCoOidRequest function forwards a request to targeted CoNDIS drivers to query or set OID-specified information of the target driver.
old-location: netvista\ndiscooidrequest.htm
old-project: netvista
ms.assetid: 7d46f2c1-7b54-4510-968a-2e35e33cf849
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: NdisCoOidRequest, ndis/NdisCoOidRequest, NdisCoOidRequest function [Network Drivers Starting with Windows Vista], netvista.ndiscooidrequest, condis_request_ref_4f9b0ee3-9096-4f13-9851-edd1f7b4af8b.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Connection_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisCoOidRequest
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---

# NdisCoOidRequest function


## -description


The 
  <b>NdisCoOidRequest</b> function forwards a request to targeted CoNDIS drivers to query or set OID-specified
  information of the target driver.


## -syntax


````
NDIS_STATUS NdisCoOidRequest(
  _In_     NDIS_HANDLE       NdisBindingHandle,
  _In_opt_ NDIS_HANDLE       NdisAfHandle,
  _In_opt_ NDIS_HANDLE       NdisVcHandle,
  _In_opt_ NDIS_HANDLE       NdisPartyHandle,
  _Inout_  PNDIS_OID_REQUEST OidRequest
);
````


## -parameters




### -param NdisBindingHandle [in]

A handle that the 
     <a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a> function returned
     that identifies the target adapter for the binding.


### -param NdisAfHandle [in, optional]

A handle that identifies the address family (AF) that is shared among the client, call manager,
     and NDIS. This handle was obtained as follows:
     

<ul>
<li>
If the caller is a client that is making a request to the call manager, the client originally
       obtained this handle from a successful call to the 
       <a href="..\ndis\nf-ndis-ndisclopenaddressfamilyex.md">
       NdisClOpenAddressFamilyEx</a> function.

</li>
<li>
If the caller is a stand-alone call manager or miniport call manager (MCM) that is making a request
       to a client, the call manager or MCM originally obtained this handle as an input parameter to its 
       <a href="..\ndis\nc-ndis-protocol_cm_open_af.md">ProtocolCmOpenAf</a> function.

</li>
</ul>
To make a request from either a client or stand-alone call manager to the underlying miniport driver,
     this parameter must be <b>NULL</b>.


### -param NdisVcHandle [in, optional]

A handle that identifies the virtual connection (VC) the caller is requesting or setting
     information for, if the request is VC-specific. Otherwise, if this parameter is <b>NULL</b>, the request is not
     VC-specific. For any VC-specific request, the caller originally obtained this handle either when it
     created the VC with the 
     <a href="..\ndis\nf-ndis-ndiscocreatevc.md">NdisCoCreateVc</a> function, or as an input
     parameter to its 
     <a href="..\ndis\nc-ndis-protocol_co_create_vc.md">ProtocolCoCreateVc</a> function. For a
     VC-specific request that is directed to the underlying miniport driver, this handle identifies the VC,
     while 
     <i>NdisAfHandle</i> and 
     <i>NdisPartyHandle</i> are <b>NULL</b>.


### -param NdisPartyHandle [in, optional]

A handle that identifies the party on a multipoint VC the caller is requesting or setting
     information for, if the request is party-specific. Otherwise, if this parameter is <b>NULL</b>, the request is
     not party-specific. For any party-specific request, a client originally obtained this handle from a
     successful call to the 
     <a href="..\ndis\nf-ndis-ndiscladdparty.md">NdisClAddParty</a> function or the 
     <a href="..\ndis\nf-ndis-ndisclmakecall.md">NdisClMakeCall</a> function or the call
     manager obtained this handle as an input parameter to its 
     <a href="..\ndis\nc-ndis-protocol_cm_add_party.md">ProtocolCmAddParty</a> function. If 
     <i>NdisAfHandle</i> is <b>NULL</b>, 
     <i>NdisPartyHandle</i> also is <b>NULL</b>.


### -param OidRequest [in, out]

A pointer to an 
     <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structure that specifies
     the operation that is requested with a given OID_<i>XXX</i> code to query or to set information.


## -returns



The target driver determines which NDIS_STATUS_<i>XXX</i> code 
     <b>NdisCoOidRequest</b> returns, usually one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The request operation completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The request is being handled asynchronously, and NDIS will call the caller's 
       <a href="..\ndis\nc-ndis-protocol_co_oid_request_complete.md">
       ProtocolCoOidRequestComplete</a> function when the request is completed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_INVALID_OID</b></dt>
</dl>
</td>
<td width="60%">
The OID_<i>XXX</i> code that was specified in the 
       <b>Oid</b> member of the 
       <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structure at the 
       <i>OidRequest</i> parameter is invalid or unsupported by the underlying driver.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_INVALID_LENGTH or NDIS_STATUS_BUFFER_TOO_SHORT</b></dt>
</dl>
</td>
<td width="60%">
The value that was specified in the 
       <b>InformationBufferLength</b> member of the NDIS_OID_REQUEST-structured buffer at 
       <i>OidRequest</i> does not match the requirements for the given OID_<i>XXX</i> code. If the information buffer is too small, the 
       <b>BytesNeeded</b> member of NDIS_OID_REQUEST contains the correct value for 
       <b>InformationBufferLength</b>, when 
       <b>NdisCoOidRequest</b> returns.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_INVALID_DATA</b></dt>
</dl>
</td>
<td width="60%">
The data supplied at 
       <b>InformationBuffer</b> in the given 
       <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structure is invalid
       for the given OID_<i>XXX</i> code.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_NOT_SUPPORTED or NDIS_STATUS_NOT_RECOGNIZED</b></dt>
</dl>
</td>
<td width="60%">
The underlying driver does not support the requested operation.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The request could not be satisfied because of a resource shortage. Usually, this return value
       indicates that an attempt to allocate memory was unsuccessful, but it does not necessarily indicate
       that the same request, if submitted later, will fail for the same reason.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_NOT_ACCEPTED</b></dt>
</dl>
</td>
<td width="60%">
The underlying driver attempted the requested operation, usually a set request, but the
       operation failed. For example, an attempt to set too many multicast addresses might cause 
       <b>NdisCoOidRequest</b> to return this value.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_CLOSING or NDIS_STATUS_CLOSING_INDICATING</b></dt>
</dl>
</td>
<td width="60%">
The underlying driver failed the requested operation because a close operation is in
       progress.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESET_IN_PROGRESS</b></dt>
</dl>
</td>
<td width="60%">
The underlying miniport driver cannot satisfy the request at this time because it is currently
       resetting the affected NIC. The caller's 
       <a href="..\ndis\nc-ndis-protocol_status_ex.md">ProtocolStatusEx</a> function was or
       will be called with NDIS_STATUS_RESET_START to indicate that a reset is in progress. This return value
       does not necessarily indicate that the same request, if submitted later, will fail for the same
       reason.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
This value usually is a nonspecific default value that is returned when none of the more
       specific NDIS_STATUS_<i>XXX</i> caused the underlying driver to fail the request.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_REQUEST_ABORTED</b></dt>
</dl>
</td>
<td width="60%">
The miniport driver stopped processing the request. For example, NDIS called an underlying
       miniport driver's 
       <a href="..\ndis\nc-ndis-miniport_reset.md">MiniportResetEx</a> or 
       <a href="..\ndis\nc-ndis-miniport_cancel_oid_request.md">
       MiniportCancelOidRequest</a> function.

</td>
</tr>
</table>
 




## -remarks



CoNDIS clients and stand-alone call managers can call the 
    <b>NdisCoOidRequest</b> function to send an OID request to query or set OID-specified information in a
    target driver. The target driver can be another CoNDIS protocol driver or an underlying driver.

The caller of 
    <b>NdisCoOidRequest</b> must allocate sufficient memory to hold the information buffer that is associated
    with the specified OID. The caller must also allocate and set up the buffer at 
    <i>OidRequest</i> before it calls 
    <b>NdisCoOidRequest</b>. Both buffers must be allocated from nonpaged pool because the target driver can
    run at raised IRQL while it processes the request.

Some errors that 
    <b>NdisCoOidRequest</b> returns are recoverable, including the following:

<ul>
<li>
NDIS_STATUS_INVALID_OID

</li>
<li>
NDIS_STATUS_INVALID_LENGTH

</li>
<li>
NDIS_STATUS_BUFFER_TOO_SHORT

</li>
<li>
NDIS_STATUS_INVALID_DATA

</li>
<li>
NDIS_STATUS_RESOURCES

</li>
<li>
NDIS_STATUS_RESET_IN_PROGRESS

</li>
</ul>
That is, a driver can modify the packet at 
    <i>OidRequest</i> appropriately to correct the OID_<i>XXX</i> code or the size or contents of the buffer at 
    <b>InformationBuffer</b> and resubmit the request packet to 
    <b>NdisCoOidRequest</b>. The same packet might be satisfied when the driver resubmits it to 
    <b>NdisCoOidRequest</b> if the original call indicated a reset in progress or that a resource shortage,
    which might be temporary, prevented that request from being carried out.

Depending on the value of the 
    <i>NdisAfHandle</i> parameter, clients and stand-alone call managers call 
    <b>NdisCoOidRequest</b> to communicate with each other or with the underlying connection-oriented miniport
    driver.

If a driver passes <b>NULL</b> for 
    <i>NdisVcHandle</i>, the request is global in nature, whether the request is directed to the client, call
    manager, or miniport driver. For example, if the caller supplies a non-<b>NULL</b> value for 
    <i>NdisVcHandle</i>, an 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff569562">OID_GEN_CO_RCV_CRC_ERROR</a> OID request
    to an underlying connection-oriented miniport driver returns the number of cyclic redundancy check (CRC)
    errors that were encountered for a particular VC. For the same request with <b>NULL</b> for 
    <i>NdisVcHandle</i>, the underlying miniport driver returns the total number of CRC errors that were
    encountered for all of the VCs.

Clients and stand-alone call managers should call the 
    <a href="..\ndis\nf-ndis-ndisoidrequest.md">NdisOidRequest</a> function for all of the OIDs
    that are not connection-oriented, such as those that are returned in an 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff569642">OID_GEN_SUPPORTED_LIST</a> query, which is
    commonly issued during initialization after the protocol driver has bound itself to the underlying NIC
    driver.

If 
    <b>NdisCoOidRequest</b> returns NDIS_STATUS_PENDING, the request is being handled asynchronously and NDIS
    will call the driver's 
    <a href="..\ndis\nc-ndis-protocol_co_oid_request_complete.md">
    ProtocolCoOidRequestComplete</a> function when the request is completed. If 
    <b>NdisCoOidRequest</b> returns any other status, the request is complete when 
    <b>NdisCoOidRequest</b> returns, and NDIS does not call 
    <i>ProtocolCoOidRequestComplete</i>.

For more information about the sets of OIDs that are defined to use with 
    <b>NdisCoOidRequest</b> and 
    <b>NdisOidRequest</b>, see 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff566707">NDIS OIDs</a>.

Only clients and stand-alone call managers, which are protocol drivers, can call 
    <b>NdisCoOidRequest</b>. MCMs call the 
    <a href="..\ndis\nf-ndis-ndismcmoidrequest.md">NdisMCmOidRequest</a> function to
    communicate with their clients.




## -see-also

<a href="..\ndis\nf-ndis-ndiscocreatevc.md">NdisCoCreateVc</a>



<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>



<a href="..\ndis\nf-ndis-ndiscladdparty.md">NdisClAddParty</a>



<a href="..\ndis\nc-ndis-protocol_cm_open_af.md">ProtocolCmOpenAf</a>



<a href="..\ndis\nf-ndis-ndisclopenaddressfamilyex.md">NdisClOpenAddressFamilyEx</a>



<a href="..\ndis\nc-ndis-miniport_reset.md">MiniportResetEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569562">OID_GEN_CO_RCV_CRC_ERROR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569642">OID_GEN_SUPPORTED_LIST</a>



<a href="..\ndis\nc-ndis-miniport_cancel_oid_request.md">MiniportCancelOidRequest</a>



<a href="..\ndis\nc-ndis-protocol_status_ex.md">ProtocolStatusEx</a>



<a href="..\ndis\nf-ndis-ndismcmoidrequest.md">NdisMCmOidRequest</a>



<a href="..\ndis\nc-ndis-protocol_cm_add_party.md">ProtocolCmAddParty</a>



<a href="..\ndis\nc-ndis-protocol_co_oid_request_complete.md">
   ProtocolCoOidRequestComplete</a>



<a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a>



<a href="..\ndis\nf-ndis-ndisoidrequest.md">NdisOidRequest</a>



<a href="..\ndis\nc-ndis-protocol_co_create_vc.md">ProtocolCoCreateVc</a>



<a href="..\ndis\nf-ndis-ndisclmakecall.md">NdisClMakeCall</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisCoOidRequest function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

