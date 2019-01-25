---
UID: NF:ndis.NdisFOidRequestComplete
title: NdisFOidRequestComplete function (ndis.h)
description: Filter drivers call the NdisFOidRequestComplete function to return the final status of an OID request for which the driver's FilterOidRequest function returned NDIS_STATUS_PENDING.
old-location: netvista\ndisfoidrequestcomplete.htm
tech.root: netvista
ms.assetid: 1d72e8e3-1053-4731-a16c-fc3e4f7460e9
ms.date: 05/02/2018
ms.keywords: NdisFOidRequestComplete, NdisFOidRequestComplete function [Network Drivers Starting with Windows Vista], ndis/NdisFOidRequestComplete, ndis_request_ref_df2bb357-d053-4f02-a828-46a72dc1fee7.xml, netvista.ndisfoidrequestcomplete
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisFOidRequestComplete function


## -description


Filter drivers call the 
  <b>NdisFOidRequestComplete</b> function to return the final status of an OID request for which the driver's 
  <a href="https://msdn.microsoft.com/238bfa21-a971-4fe4-a774-6ba834efc3c5">FilterOidRequest</a> function returned
  NDIS_STATUS_PENDING.


## -parameters




### -param NdisFilterHandle [in]

The NDIS handle that identifies this filter module. NDIS passed the handle to the filter driver in
     a call to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-filter_attach">FilterAttach</a> function.


### -param OidRequest [in]

A pointer to a buffer formatted as an 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a> structure. The filter
     driver obtained this pointer as an input parameter to its 
     <a href="https://msdn.microsoft.com/238bfa21-a971-4fe4-a774-6ba834efc3c5">FilterOidRequest</a> function.


### -param Status [in]

The final status of the request operation, either NDIS_STATUS_SUCCESS or any driver-determined
     NDIS_STATUS_<i>XXX</i> value except NDIS_STATUS_PENDING.


## -returns



None




## -remarks



A filter driver that returns NDIS_STATUS_PENDING from its 
    <a href="https://msdn.microsoft.com/238bfa21-a971-4fe4-a774-6ba834efc3c5">FilterOidRequest</a> function must call
    the 
    <b>NdisFOidRequestComplete</b> function after the driver has finished the request operation.

If an overlying driver originated the OID request, NDIS calls the request complete function of the
    overlying driver after the filter driver calls 
    <b>NdisFOidRequestComplete</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-filter_attach">FilterAttach</a>



<a href="https://msdn.microsoft.com/238bfa21-a971-4fe4-a774-6ba834efc3c5">FilterOidRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a>
 

 

