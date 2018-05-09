---
UID: NF:ndis.NdisMOidRequestComplete
title: NdisMOidRequestComplete function
author: windows-driver-content
description: Miniport drivers call the NdisMOidRequestComplete function to return the final status of an OID request for which the driver's MiniportOidRequest function returned NDIS_STATUS_PENDING.
old-location: netvista\ndismoidrequestcomplete.htm
old-project: netvista
ms.assetid: 30d060d0-05a3-42b5-b5ff-2f2b12873ca9
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: NdisMOidRequestComplete, NdisMOidRequestComplete function [Network Drivers Starting with Windows Vista], ndis/NdisMOidRequestComplete, ndis_request_ref_b5524732-acaf-4d0d-a261-3f8a8b739ecc.xml, netvista.ndismoidrequestcomplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: DoubleComplete, DoubleCompleteWorkItem, Irql_OID_Function, NdisMNetPnPEventInOIDRequest, NdisOidComplete, NdisOidDoubleComplete, NdisOidDoubleRequest, NdisTimedOidComplete, WlanAssociation, WlanDisassociation, WlanTimedConnectRequest, WlanTimedLinkQuality, WlanTimedScan
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
-	NdisMOidRequestComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMOidRequestComplete function


## -description


Miniport drivers call the 
  <b>NdisMOidRequestComplete</b> function to return the final status of an OID request for which the driver's 
  <a href="https://msdn.microsoft.com/733d84f5-c1d4-42a0-a59b-4ba50247f165">MiniportOidRequest</a> function returned
  NDIS_STATUS_PENDING.


## -parameters




### -param MiniportAdapterHandle [in]

A miniport adapter handle that NDIS passed to the 
     <i>MiniportAdapterHandle</i> parameter of the 
     <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">
     MiniportInitializeEx</a> function.


### -param OidRequest [in]

A pointer to a buffer that is formatted as an 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a> structure. The miniport
     driver obtained this pointer as an input parameter to its 
     <i>MiniportOidRequest</i> function.


### -param Status [in]

The final status of the request operation, either NDIS_STATUS_SUCCESS,
     NDIS_STATUS_REQUEST_ABORTED, or any driver-determined NDIS_STATUS_<i>XXX</i><u>except</u> NDIS_STATUS_PENDING. For more information about OID status values, see 
     <a href="https://msdn.microsoft.com/733d84f5-c1d4-42a0-a59b-4ba50247f165">MiniportOidRequest</a>.


## -returns



None




## -remarks



A miniport driver that returns NDIS_STATUS_PENDING from its 
    <a href="https://msdn.microsoft.com/733d84f5-c1d4-42a0-a59b-4ba50247f165">MiniportOidRequest</a> function must
    call 
    <b>NdisMOidRequestComplete</b> after the miniport driver has finished the request operation.

A call to 
    <b>NdisMOidRequestComplete</b> causes a call to the request complete function (see 
    <a href="https://msdn.microsoft.com/2c383523-7d9c-4f1b-8df1-5cb4cc3562d6">ProtocolRequestComplete</a>, 
    <a href="https://msdn.microsoft.com/2706577e-ba03-4347-9672-7303752ec0fe">ProtocolOidRequestComplete</a>,
    
    <a href="https://msdn.microsoft.com/2dba21d8-512b-4a1a-9cf9-0240c94a69a0">FilterOidRequestComplete</a>) of
    the overlying driver that called the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff563710">NdisOidRequest</a> function.




## -see-also




<a href="https://msdn.microsoft.com/2dba21d8-512b-4a1a-9cf9-0240c94a69a0">FilterOidRequestComplete</a>



<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/733d84f5-c1d4-42a0-a59b-4ba50247f165">MiniportOidRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563710">NdisOidRequest</a>



<a href="https://msdn.microsoft.com/2706577e-ba03-4347-9672-7303752ec0fe">ProtocolOidRequestComplete</a>



<a href="https://msdn.microsoft.com/2c383523-7d9c-4f1b-8df1-5cb4cc3562d6">ProtocolRequestComplete</a>
 

 

