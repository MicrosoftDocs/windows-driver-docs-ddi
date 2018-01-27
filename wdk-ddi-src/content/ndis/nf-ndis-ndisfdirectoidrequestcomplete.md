---
UID: NF:ndis.NdisFDirectOidRequestComplete
title: NdisFDirectOidRequestComplete function
author: windows-driver-content
description: Filter drivers call the NdisFDirectOidRequestComplete function to return the final status of a direct OID request for which the driver's FilterDirectOidRequest function returned NDIS_STATUS_PENDING.
old-location: netvista\ndisfdirectoidrequestcomplete.htm
old-project: netvista
ms.assetid: b6b4d4f4-63d5-496c-9082-f2e8d1a174ec
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NdisFDirectOidRequestComplete function [Network Drivers Starting with Windows Vista], ndis_request_direct_ref_b61f2fdf-0fb8-4df8-8637-a4db671d008f.xml, netvista.ndisfdirectoidrequestcomplete, NdisFDirectOidRequestComplete, ndis/NdisFDirectOidRequestComplete
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
-	NdisFDirectOidRequestComplete
product: Windows
targetos: Windows
req.typenames: *PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE
---

# NdisFDirectOidRequestComplete function


## -description


Filter drivers call the 
  <b>NdisFDirectOidRequestComplete</b> function to return the final status of a direct OID request for which
  the driver's 
  <a href="..\ndis\nc-ndis-filter_direct_oid_request.md">FilterDirectOidRequest</a> function
  returned NDIS_STATUS_PENDING.


## -syntax


````
VOID NdisFDirectOidRequestComplete(
  _In_ NDIS_HANDLE       NdisFilterHandle,
  _In_ PNDIS_OID_REQUEST OidRequest,
  _In_ NDIS_STATUS       Status
);
````


## -parameters




### -param NdisFilterHandle [in]

The NDIS handle that identifies this filter module NDIS passed the handle to the filter driver in
     a call to the 
     <a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a> function.


### -param OidRequest [in]

A pointer to a buffer that is formatted as an 
     <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structure. The filter
     driver obtained this pointer as an input parameter to its 
     <mshelp:link keywords="netvista.filterdirectoidrequest" tabindex="0"><i>
     FilterDirectOidRequest</i></mshelp:link> function.


### -param Status [in]

The final status of the request operation: NDIS_STATUS_SUCCESS or any driver-determined
     NDIS_STATUS_<i>Xxx</i> value except NDIS_STATUS_PENDING.


## -returns


None



## -remarks


A filter driver that returns NDIS_STATUS_PENDING from its 
    <a href="..\ndis\nc-ndis-filter_direct_oid_request.md">FilterDirectOidRequest</a> function
    must call the 
    <b>NdisFDirectOidRequestComplete</b> function after the driver has finished the request operation.

If an overlying driver originated the direct OID request, NDIS calls the request complete function
    (see 
    <mshelp:link keywords="netvista.protocoldirectoidrequestcomplete" tabindex="0"><i>
    ProtocolDirectOidRequestComplete</i></mshelp:link> and 
    <mshelp:link keywords="netvista.filterdirectoidrequestcomplete" tabindex="0"><i>
    FilterDirectOidRequestComplete</i></mshelp:link>) of the overlying driver that originated the request.



## -see-also

<a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a>

<mshelp:link keywords="netvista.filterdirectoidrequestcomplete" tabindex="0"><i>
   FilterDirectOidRequestComplete</i></mshelp:link>

<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>

<mshelp:link keywords="netvista.protocoldirectoidrequestcomplete" tabindex="0"><i>
   ProtocolDirectOidRequestComplete</i></mshelp:link>

<a href="..\ndis\nc-ndis-filter_direct_oid_request.md">FilterDirectOidRequest</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisFDirectOidRequestComplete function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

