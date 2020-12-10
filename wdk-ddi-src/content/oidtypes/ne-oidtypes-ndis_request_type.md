---
UID: NE:oidtypes._NDIS_REQUEST_TYPE
title: NDIS_REQUEST_TYPE
ms.date: 11/30/2020
ms.topic: language-reference
targetos: Windows
description: The NDIS_REQUEST_TYPE enumeration identifies the request type in an OID request.
tech.root: netvista 
req.construct-type: enumeration
req.ddi-compliance: 
req.header: ndis/oidtypes.h
req.include-header: ndis.h
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.target-type: Windows
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - oidtypes.h
api_name:
 - _NDIS_REQUEST_TYPE
 - PNDIS_REQUEST_TYPE
 - NDIS_REQUEST_TYPE
f1_keywords:
 - _NDIS_REQUEST_TYPE
 - oidtypes/_NDIS_REQUEST_TYPE
 - PNDIS_REQUEST_TYPE
 - oidtypes/PNDIS_REQUEST_TYPE
 - NDIS_REQUEST_TYPE
 - oidtypes/NDIS_REQUEST_TYPE
dev_langs:
 - c++
---

# _NDIS_REQUEST_TYPE enumeration


## -description

The NDIS_REQUEST_TYPE enumeration identifies the request type in an OID request.

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
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_oid_request">MiniportOidRequest</a> function.

## -remarks

The NDIS_REQUEST_TYPE enumeration is used in the 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a> structure.

<div class="alert"><b>Note</b>  For any NDIS_REQUEST_TYPE value, the OID_<i>Xxx</i> that is specified in the 
    <b>Oid</b> member of the NDIS_OID_REQUEST structure must be compatible with the type of operation
    requested.</div>
<div> </div>

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_oid_request">MiniportOidRequest</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a>
