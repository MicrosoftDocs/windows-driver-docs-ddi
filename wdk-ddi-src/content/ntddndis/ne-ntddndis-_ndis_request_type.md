---
UID: NE:ntddndis._NDIS_REQUEST_TYPE
title: "_NDIS_REQUEST_TYPE"
author: windows-driver-content
description: The NDIS_REQUEST_TYPE enumeration identifies the request type in an OID request.
old-location: netvista\ndis_request_type.htm
old-project: netvista
ms.assetid: c4352eab-8bbd-429e-93ad-190372d29f2c
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddndis/NdisRequestGeneric1, NdisRequestReset, NdisRequestQueryStatistics, NdisRequestGeneric4, ntddndis/NdisRequestGeneric2, ntddndis/NdisRequestGeneric3, *PNDIS_REQUEST_TYPE, ntddndis/PNDIS_REQUEST_TYPE, NdisRequestClose, ntddndis/NdisRequestGeneric4, NdisRequestOpen, NDIS_REQUEST_TYPE, ntddndis/NdisRequestQueryInformation, ndis_request_ref_78880aa3-bab2-49bd-9232-117accb98ce3.xml, ntddndis/NdisRequestSetInformation, ntddndis/NdisRequestTransferData, ntddndis/NdisRequestMethod, ntddndis/NdisRequestOpen, NdisRequestMethod, ntddndis/NdisRequestReset, PNDIS_REQUEST_TYPE enumeration pointer [Network Drivers Starting with Windows Vista], ntddndis/NdisRequestQueryStatistics, NdisRequestGeneric3, PNDIS_REQUEST_TYPE, ntddndis/NDIS_REQUEST_TYPE, NdisRequestGeneric1, _NDIS_REQUEST_TYPE, NDIS_REQUEST_TYPE enumeration [Network Drivers Starting with Windows Vista], NdisRequestTransferData, NdisRequestGeneric2, NdisRequestSend, netvista.ndis_request_type, NdisRequestQueryInformation, ntddndis/NdisRequestSend, NdisRequestSetInformation, ntddndis/NdisRequestClose
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddndis.h
apiname:
-	NDIS_REQUEST_TYPE
product: Windows
targetos: Windows
req.typenames: "*PNDIS_REQUEST_TYPE, NDIS_REQUEST_TYPE"
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




#### - NdisRequestQueryInformation

A query-information request. For certain requests, NDIS satisfies the request. Otherwise,
     NDIS forwards such requests to the underlying driver's 
     <i>MiniportOidRequest</i> function. This type of request can originate in a user-mode application, filter module, or protocol driver.
<div class="alert"><b>Note</b>  Drivers should treat <b>NdisRequestQueryInformation</b> and <b>NdisRequestQueryStatistics</b> queries identically.</div><div> </div>

#### - NdisRequestSetInformation

A set-information request. NDIS forwards such a request to the underlying driver's 
     <i>MiniportOidRequest</i> function.


#### - NdisRequestQueryStatistics

A query-statistics request. For certain requests, NDIS satisfies the request. Otherwise,
     NDIS forwards such requests to the underlying driver's 
     <i>MiniportOidRequest</i> function. This type of request can originate in a user-mode application, filter module, or protocol driver.
<div class="alert"><b>Note</b>  Drivers should treat <b>NdisRequestQueryInformation</b> and <b>NdisRequestQueryStatistics</b> queries identically.</div><div> </div>

#### - NdisRequestOpen

This type is obsolete.


#### - NdisRequestClose

This type is obsolete.


#### - NdisRequestSend

This type is obsolete.


#### - NdisRequestTransferData

This type is obsolete.


#### - NdisRequestReset

This type is obsolete.


#### - NdisRequestGeneric1

A request that is specific to the type of the miniport driver.


#### - NdisRequestGeneric2

A request that is specific to the type of the miniport driver.


#### - NdisRequestGeneric3

A request that is specific to the type of the miniport driver.


#### - NdisRequestGeneric4

A request that is specific to the type of the miniport driver.


#### - NdisRequestMethod

A method request. NDIS forwards such a request to the underlying driver's 
     <a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a> function.


## -remarks


The NDIS_REQUEST_TYPE enumeration is used in the 
    <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structure.
<div class="alert"><b>Note</b>  For any NDIS_REQUEST_TYPE value, the OID_<i>Xxx</i> that is specified in the 
    <b>Oid</b> member of the NDIS_OID_REQUEST structure must be compatible with the type of operation
    requested.</div><div> </div>


## -see-also

<a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a>

<a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_REQUEST_TYPE enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

