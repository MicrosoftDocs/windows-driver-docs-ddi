---
UID: NE:ntddndis._NDIS_REQUEST_TYPE
title: _NDIS_REQUEST_TYPE
author: windows-driver-content
description: The NDIS_REQUEST_TYPE enumeration identifies the request type in an OID request.
old-location: netvista\ndis_request_type.htm
old-project: netvista
ms.assetid: c4352eab-8bbd-429e-93ad-190372d29f2c
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _NDIS_REQUEST_TYPE, NDIS_REQUEST_TYPE, *PNDIS_REQUEST_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_REQUEST_TYPE
req.alt-loc: Ntddndis.h
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
req.typenames: NDIS_REQUEST_TYPE, *PNDIS_REQUEST_TYPE
---

# _NDIS_REQUEST_TYPE enumeration



## -description
The NDIS_REQUEST_TYPE enumeration identifies the request type in an OID request.



## -syntax

````
typedef enum _NDIS_REQUEST_TYPE { 
  NdisRequestQueryInformation,
  NdisRequestSetInformation,
  NdisRequestQueryStatistics,
  NdisRequestOpen,
  NdisRequestClose,
  NdisRequestSend,
  NdisRequestTransferData,
  NdisRequestReset,
  NdisRequestGeneric1,
  NdisRequestGeneric2,
  NdisRequestGeneric3,
  NdisRequestGeneric4,
  NdisRequestMethod
} NDIS_REQUEST_TYPE, *PNDIS_REQUEST_TYPE;
````


## -enum-fields

### -field NdisRequestQueryInformation

A query-information request. For certain requests, NDIS satisfies the request. Otherwise,
     NDIS forwards such requests to the underlying driver's 
     <i>MiniportOidRequest</i> function. This type of request can originate in a user-mode application, filter module, or protocol driver.

<div class="alert"><b>Note</b>  Drivers should treat <b>NdisRequestQueryInformation</b> and <b>NdisRequestQueryStatistics</b> queries identically.</div>
<div> </div>

### -field NdisRequestSetInformation

A set-information request. NDIS forwards such a request to the underlying driver's 
     <i>MiniportOidRequest</i> function.


### -field NdisRequestQueryStatistics

A query-statistics request. For certain requests, NDIS satisfies the request. Otherwise,
     NDIS forwards such requests to the underlying driver's 
     <i>MiniportOidRequest</i> function. This type of request can originate in a user-mode application, filter module, or protocol driver.

<div class="alert"><b>Note</b>  Drivers should treat <b>NdisRequestQueryInformation</b> and <b>NdisRequestQueryStatistics</b> queries identically.</div>
<div> </div>

### -field NdisRequestOpen

This type is obsolete.


### -field NdisRequestClose

This type is obsolete.


### -field NdisRequestSend

This type is obsolete.


### -field NdisRequestTransferData

This type is obsolete.


### -field NdisRequestReset

This type is obsolete.


### -field NdisRequestGeneric1

A request that is specific to the type of the miniport driver.


### -field NdisRequestGeneric2

A request that is specific to the type of the miniport driver.


### -field NdisRequestGeneric3

A request that is specific to the type of the miniport driver.


### -field NdisRequestGeneric4

A request that is specific to the type of the miniport driver.


### -field NdisRequestMethod

A method request. NDIS forwards such a request to the underlying driver's 
     <a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a> function.


## -remarks
The NDIS_REQUEST_TYPE enumeration is used in the 
    <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structure.


## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_REQUEST_TYPE enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

