---
UID: NF:ndis.NdisFDirectOidRequest
title: NdisFDirectOidRequest function
author: windows-driver-content
description: Filter drivers call the NdisFDirectOidRequest function to forward a direct OID request to underlying drivers or to originate such a request.
old-location: netvista\ndisfdirectoidrequest.htm
old-project: netvista
ms.assetid: dec5415b-6903-416e-819b-007ea6f7e7b5
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NdisFDirectOidRequest, netvista.ndisfdirectoidrequest, NdisFDirectOidRequest function [Network Drivers Starting with Windows Vista], ndis_request_direct_ref_f29e3367-5ebb-43af-bea8-d8729436ee17.xml, ndis/NdisFDirectOidRequest
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.1 and later.
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
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	LibDef
apilocation: 
-	ndis.lib
-	ndis.dll
apiname: 
-	NdisFDirectOidRequest
product: Windows
targetos: Windows
req.typenames: *PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE
---

# NdisFDirectOidRequest function


## -description


Filter drivers call the 
  <b>NdisFDirectOidRequest</b> function to forward a direct OID request to underlying drivers or to originate
  such a request.


## -syntax


````
NDIS_STATUS NdisFDirectOidRequest(
  _In_ NDIS_HANDLE       NdisFilterHandle,
  _In_ PNDIS_OID_REQUEST OidRequest
);
````


## -parameters




### -param NdisFilterHandle [in]

An NDIS handle that identifies a filter module. NDIS passed the handle to the filter driver in a
     call to the 
     <a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a> function.


### -param OidRequest [in]

A pointer to an 
     <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structure that specifies
     the operation that is requested with a given OID_<i>Xxx</i> code. The structure can specify an OID query, set, or method request.


## -returns


For a list of possible return values, see the 
     <a href="..\ndis\nf-ndis-ndisdirectoidrequest.md">NdisDirectOidRequest</a> function.



## -remarks


The 
    <b>NdisFDirectOidRequest</b> function cannot be used for general OID requests. For general OID requests,
    use the 
    <a href="..\ndis\nf-ndis-ndisfoidrequest.md">NdisFOidRequest</a> function instead. 
    <b>NdisFDirectOidRequest</b> can be used only for OIDs that NDIS supports for use with the direct OID
    interface. For example, the following OIDs can be used:


<mshelp:link keywords="netvista.oid_tcp_task_ipsec_offload_v2_add_sa" tabindex="0">
       OID_TCP_TASK_IPSEC_OFFLOAD_V2_ADD_SA</mshelp:link>



<mshelp:link keywords="netvista.oid_tcp_task_ipsec_offload_v2_delete_sa" tabindex="0">
       OID_TCP_TASK_IPSEC_OFFLOAD_V2_DELETE_SA</mshelp:link>



<mshelp:link keywords="netvista.oid_tcp_task_ipsec_offload_v2_update_sa" tabindex="0">
       OID_TCP_TASK_IPSEC_OFFLOAD_V2_UPDATE_SA</mshelp:link>


Filter drivers can originate direct OID requests to underlying drivers by calling 
    <b>NdisFDirectOidRequest</b>.

Filter drivers can also filter direct OID requests that are originated by overlying drivers. NDIS
    calls the 
    <a href="..\ndis\nc-ndis-filter_direct_oid_request.md">FilterDirectOidRequest</a> function
    to process each such request.

If 
    <b>NdisFDirectOidRequest</b> returns <b>NDIS_STATUS_PENDING</b>, NDIS calls the 
    <a href="..\ndis\nc-ndis-filter_direct_oid_request_complete.md">FilterDirectOidRequestComplete</a> function after the underlying drivers complete the OID request. A
    driver that calls 
    <b>NdisFDirectOidRequest</b> must register the 
    <i>FilterDirectOidRequestComplete</i> function.

A driver can call 
    <b>NdisFDirectOidRequest</b> when it is in the 
    <i>Restarting</i>, 
    <i>Running</i>, 
    <i>Pausing</i>, or 
    <i>Paused</i> state.

The direct OID request interface is similar to the general OID request interface. For more information
    about issuing general requests, see 
    <a href="..\ndis\nf-ndis-ndisfoidrequest.md">NdisFOidRequest</a>.



## -see-also

<mshelp:link keywords="netvista.oid_tcp_task_ipsec_offload_v2_update_sa" tabindex="0">
   OID_TCP_TASK_IPSEC_OFFLOAD_V2_UPDATE_SA</mshelp:link>

<a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a>

<mshelp:link keywords="netvista.filterdirectoidrequestcomplete" tabindex="0"><i>
   FilterDirectOidRequestComplete</i></mshelp:link>

<mshelp:link keywords="netvista.oid_tcp_task_ipsec_offload_v2_add_sa" tabindex="0">
   OID_TCP_TASK_IPSEC_OFFLOAD_V2_ADD_SA</mshelp:link>

<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>

<a href="..\ndis\nf-ndis-ndisdirectoidrequest.md">NdisDirectOidRequest</a>

<a href="..\ndis\nf-ndis-ndisfoidrequest.md">NdisFOidRequest</a>

<mshelp:link keywords="netvista.oid_tcp_task_ipsec_offload_v2_delete_sa" tabindex="0">
   OID_TCP_TASK_IPSEC_OFFLOAD_V2_DELETE_SA</mshelp:link>

<a href="..\ndis\nc-ndis-filter_direct_oid_request.md">FilterDirectOidRequest</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisFDirectOidRequest function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

