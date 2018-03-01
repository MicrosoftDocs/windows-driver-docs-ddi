---
UID: NF:ndis.NdisFOidRequestComplete
title: NdisFOidRequestComplete function
author: windows-driver-content
description: Filter drivers call the NdisFOidRequestComplete function to return the final status of an OID request for which the driver's FilterOidRequest function returned NDIS_STATUS_PENDING.
old-location: netvista\ndisfoidrequestcomplete.htm
old-project: netvista
ms.assetid: 1d72e8e3-1053-4731-a16c-fc3e4f7460e9
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: NdisFOidRequestComplete, NdisFOidRequestComplete function [Network Drivers Starting with Windows Vista], ndis/NdisFOidRequestComplete, ndis_request_ref_df2bb357-d053-4f02-a828-46a72dc1fee7.xml, netvista.ndisfoidrequestcomplete
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
req.ddi-compliance: Irql_OID_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisFOidRequestComplete
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisFOidRequestComplete function


## -description


Filter drivers call the 
  <b>NdisFOidRequestComplete</b> function to return the final status of an OID request for which the driver's 
  <a href="..\ndis\nc-ndis-filter_oid_request.md">FilterOidRequest</a> function returned
  NDIS_STATUS_PENDING.


## -syntax


````
VOID NdisFOidRequestComplete(
  _In_ NDIS_HANDLE       NdisFilterHandle,
  _In_ PNDIS_OID_REQUEST OidRequest,
  _In_ NDIS_STATUS       Status
);
````


## -parameters




### -param NdisFilterHandle [in]

The NDIS handle that identifies this filter module. NDIS passed the handle to the filter driver in
     a call to the 
     <a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a> function.


### -param OidRequest [in]

A pointer to a buffer formatted as an 
     <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structure. The filter
     driver obtained this pointer as an input parameter to its 
     <a href="..\ndis\nc-ndis-filter_oid_request.md">FilterOidRequest</a> function.


### -param Status [in]

The final status of the request operation, either NDIS_STATUS_SUCCESS or any driver-determined
     NDIS_STATUS_<i>XXX</i> value except NDIS_STATUS_PENDING.


## -returns



None




## -remarks



A filter driver that returns NDIS_STATUS_PENDING from its 
    <a href="..\ndis\nc-ndis-filter_oid_request.md">FilterOidRequest</a> function must call
    the 
    <b>NdisFOidRequestComplete</b> function after the driver has finished the request operation.

If an overlying driver originated the OID request, NDIS calls the request complete function of the
    overlying driver after the filter driver calls 
    <b>NdisFOidRequestComplete</b>.




## -see-also

<a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a>



<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>



<a href="..\ndis\nc-ndis-filter_oid_request.md">FilterOidRequest</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisFOidRequestComplete function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

