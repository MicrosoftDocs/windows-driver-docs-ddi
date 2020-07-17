---
UID: NF:ndis.NdisMCmOidRequestComplete
title: NdisMCmOidRequestComplete macro (ndis.h)
description: The NdisMCmOidRequestComplete function returns the final status of a CoNDIS OID requestthat a miniport call manager (MCM) driver's ProtocolCoOidRequest function previously returned NDIS_STATUS_PENDING for.
old-location: netvista\ndismcmoidrequestcomplete.htm
tech.root: netvista
ms.assetid: 4c45be9f-3d07-4150-830a-3aa6d74531ff
ms.date: 05/02/2018
keywords: ["NdisMCmOidRequestComplete macro"]
ms.keywords: NdisMCmOidRequestComplete, NdisMCmOidRequestComplete macro [Network Drivers Starting with Windows Vista], condis_request_ref_fc46ea1a-b820-4f1d-b986-e879adb27ad6.xml, ndis/NdisMCmOidRequestComplete, netvista.ndismcmoidrequestcomplete
f1_keywords:
 - "ndis/NdisMCmOidRequestComplete"
 - "NdisMCmOidRequestComplete"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_MCM_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ndis.h
api_name:
- NdisMCmOidRequestComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMCmOidRequestComplete macro


## -description


The 
  <b>NdisMCmOidRequestComplete</b> function returns the final status of a CoNDIS OID requestthat a miniport
  call manager (MCM) driver's 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_oid_request">ProtocolCoOidRequest</a> function
  previously returned NDIS_STATUS_PENDING for.


## -parameters




### -param _AH_

An address family (AF) handle that NDIS passed to the MCM's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_oid_request">
     ProtocolCoOidRequest</a> function.

### -param _VH_

A virtual connection (VC) handle that NDIS passed to the MCM's 
     <i>ProtocolCoOidRequest</i> function. A <b>NULL</b> value for this parameter indicates that the request is not
     VC-specific. This parameter is <b>NULL</b> if the caller of the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscooidrequest">NdisCoOidRequest</a> function specified a
     <b>NULL</b> VC handle.

### -param _PH_

A party handle that NDIS passed to the MCM's 
     <i>ProtocolCoOidRequest</i> function. A <b>NULL</b> value for this parameter indicates that the request is not
     party-specific. This parameter is <b>NULL</b> if the caller of the 
     <b>NdisCoOidRequest</b> function specified a <b>NULL</b> party handle.

### -param _R_

A pointer to an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a> structure that the caller
     of the 
     <b>NdisCoOidRequest</b> function supplied.

### -param _S_

The final status of the request operation. This parameter can be NDIS_STATUS_SUCCESS,
     NDIS_STATUS_REQUEST_ABORTED, or any driver-determined NDIS_STATUS_<i>XXX</i> status value
     <u>except</u> NDIS_STATUS_PENDING.
     
## -remarks



A CoNDIS MCM that returns NDIS_STATUS_PENDING from its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_oid_request">ProtocolCoOidRequest</a> function must
    call the 
    <b>NdisMCmOidRequestComplete</b> function after the MCM has finished the OID request operation.

After the MCM calls 
    <b>NdisMCmOidRequestComplete</b>, NDIS calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_oid_request_complete">
    ProtocolCoOidRequestComplete</a> function of the CoNDIS client that originally called the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscooidrequest">NdisCoOidRequest</a> function.

For more information about the OIDs defined to use with CONDIS drivers, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_netvista/">NDIS OIDs</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscooidrequest">NdisCoOidRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_oid_request">ProtocolCoOidRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_oid_request_complete">
   ProtocolCoOidRequestComplete</a>
 

 

