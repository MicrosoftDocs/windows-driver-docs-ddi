---
UID: NF:ndis.NdisMDirectOidRequestComplete
title: NdisMDirectOidRequestComplete function
author: windows-driver-content
description: Miniport drivers call the NdisMDirectOidRequestComplete function to return the final status of a direct OID request for which the driver's MiniportDirectOidRequest function returned NDIS_STATUS_PENDING.
old-location: netvista\ndismdirectoidrequestcomplete.htm
old-project: netvista
ms.assetid: 11b8d4ed-54c8-4c64-ba9d-2a6fc1b22724
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: NdisMDirectOidRequestComplete, NdisMDirectOidRequestComplete function [Network Drivers Starting with Windows Vista], ndis/NdisMDirectOidRequestComplete, ndis_request_direct_ref_5f09825b-962f-41a9-b25d-e21c20e23249.xml, netvista.ndismdirectoidrequestcomplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
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
-	NdisMDirectOidRequestComplete
product: Windows
targetos: Windows
req.typenames: 
---

# NdisMDirectOidRequestComplete function


## -description


Miniport drivers call the 
  <b>NdisMDirectOidRequestComplete</b> function to return the final status of a direct OID request for which
  the driver's 
  <a href="https://msdn.microsoft.com/60daba60-3e04-4e98-a458-4dc263f17761">
  MiniportDirectOidRequest</a> function returned NDIS_STATUS_PENDING.


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
     <i>MiniportDirectOidRequest</i> function.


### -param Status [in]

The final status of the request operation: NDIS_STATUS_SUCCESS, NDIS_STATUS_REQUEST_ABORTED, or
     any driver-determined NDIS_STATUS_<i>Xxx</i><u>except</u> NDIS_STATUS_PENDING. For more information about OID status values, see 
     <a href="https://msdn.microsoft.com/60daba60-3e04-4e98-a458-4dc263f17761">
     MiniportDirectOidRequest</a>.


## -returns



None




## -remarks



A miniport driver that returns NDIS_STATUS_PENDING from its 
    <a href="https://msdn.microsoft.com/60daba60-3e04-4e98-a458-4dc263f17761">
    MiniportDirectOidRequest</a> function must call 
    <b>NdisMDirectOidRequestComplete</b> after the miniport driver has finished the request operation.

If an overlying driver originated the direct OID request, NDIS calls the request complete function
    (see 
    <a href="https://msdn.microsoft.com/6b23bbba-1b18-4da7-a45c-68df7c960aad">
    ProtocolDirectOidRequestComplete</a> and 
    <a href="https://msdn.microsoft.com/a97c86e9-4fd9-4e2f-9787-4fa19c38a69b">
    FilterDirectOidRequestComplete</a>) of the overlying that originated the request.




## -see-also




<a href="https://msdn.microsoft.com/a97c86e9-4fd9-4e2f-9787-4fa19c38a69b">
   FilterDirectOidRequestComplete</a>



<a href="https://msdn.microsoft.com/60daba60-3e04-4e98-a458-4dc263f17761">MiniportDirectOidRequest</a>



<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a>



<a href="https://msdn.microsoft.com/6b23bbba-1b18-4da7-a45c-68df7c960aad">
   ProtocolDirectOidRequestComplete</a>
 

 

