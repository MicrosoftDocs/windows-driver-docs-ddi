---
UID: NF:ndis.NdisFDirectOidRequestComplete
title: NdisFDirectOidRequestComplete function
author: windows-driver-content
description: Filter drivers call the NdisFDirectOidRequestComplete function to return the final status of a direct OID request for which the driver's FilterDirectOidRequest function returned NDIS_STATUS_PENDING.
old-location: netvista\ndisfdirectoidrequestcomplete.htm
tech.root: netvista
ms.assetid: b6b4d4f4-63d5-496c-9082-f2e8d1a174ec
ms.date: 5/2/2018
ms.keywords: NdisFDirectOidRequestComplete, NdisFDirectOidRequestComplete function [Network Drivers Starting with Windows Vista], ndis/NdisFDirectOidRequestComplete, ndis_request_direct_ref_b61f2fdf-0fb8-4df8-8637-a4db671d008f.xml, netvista.ndisfdirectoidrequestcomplete
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
-	NdisFDirectOidRequestComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisFDirectOidRequestComplete function


## -description


Filter drivers call the 
  <b>NdisFDirectOidRequestComplete</b> function to return the final status of a direct OID request for which
  the driver's 
  <a href="https://msdn.microsoft.com/a39f4b50-0183-4f92-82f2-3c8e2e2d0632">FilterDirectOidRequest</a> function
  returned NDIS_STATUS_PENDING.


## -parameters




### -param NdisFilterHandle [in]

The NDIS handle that identifies this filter module NDIS passed the handle to the filter driver in
     a call to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff540442">FilterAttach</a> function.


### -param OidRequest [in]

A pointer to a buffer that is formatted as an 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a> structure. The filter
     driver obtained this pointer as an input parameter to its 
     <a href="https://msdn.microsoft.com/a39f4b50-0183-4f92-82f2-3c8e2e2d0632">
     FilterDirectOidRequest</a> function.


### -param Status [in]

The final status of the request operation: NDIS_STATUS_SUCCESS or any driver-determined
     NDIS_STATUS_<i>Xxx</i> value except NDIS_STATUS_PENDING.


## -returns



None




## -remarks



A filter driver that returns NDIS_STATUS_PENDING from its 
    <a href="https://msdn.microsoft.com/a39f4b50-0183-4f92-82f2-3c8e2e2d0632">FilterDirectOidRequest</a> function
    must call the 
    <b>NdisFDirectOidRequestComplete</b> function after the driver has finished the request operation.

If an overlying driver originated the direct OID request, NDIS calls the request complete function
    (see 
    <a href="https://msdn.microsoft.com/6b23bbba-1b18-4da7-a45c-68df7c960aad">
    ProtocolDirectOidRequestComplete</a> and 
    <a href="https://msdn.microsoft.com/a97c86e9-4fd9-4e2f-9787-4fa19c38a69b">
    FilterDirectOidRequestComplete</a>) of the overlying driver that originated the request.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540442">FilterAttach</a>



<a href="https://msdn.microsoft.com/a39f4b50-0183-4f92-82f2-3c8e2e2d0632">FilterDirectOidRequest</a>



<a href="https://msdn.microsoft.com/a97c86e9-4fd9-4e2f-9787-4fa19c38a69b">
   FilterDirectOidRequestComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a>



<a href="https://msdn.microsoft.com/6b23bbba-1b18-4da7-a45c-68df7c960aad">
   ProtocolDirectOidRequestComplete</a>
 

 

