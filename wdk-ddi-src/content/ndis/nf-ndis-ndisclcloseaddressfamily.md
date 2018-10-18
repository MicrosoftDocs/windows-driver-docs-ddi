---
UID: NF:ndis.NdisClCloseAddressFamily
title: NdisClCloseAddressFamily function
author: windows-driver-content
description: NdisClCloseAddressFamily releases the association between a client protocol and a call manager's or MCM driver's registered AF for a particular NIC to which the client is bound.
old-location: netvista\ndisclcloseaddressfamily.htm
tech.root: netvista
ms.assetid: ae6b9133-bb98-4858-bef5-1cbe0ae0dd4f
ms.date: 5/2/2018
ms.keywords: NdisClCloseAddressFamily, NdisClCloseAddressFamily function [Network Drivers Starting with Windows Vista], condis_client_ref_6aa6db12-2ebe-444a-a239-46542dd1be4a.xml, ndis/NdisClCloseAddressFamily, netvista.ndisclcloseaddressfamily
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisClCloseAddressFamily (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisClCloseAddressFamily (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Protocol_Driver_Function
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
-	NdisClCloseAddressFamily
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisClCloseAddressFamily function


## -description


<b>NdisClCloseAddressFamily</b> releases
  the association between a client protocol and a call manager's or MCM driver's registered AF for a
  particular NIC to which the client is bound.


## -parameters




### -param NdisAfHandle [in]

Specifies the NDIS-supplied handle returned by 
     <a href="https://msdn.microsoft.com/54170917-60b4-4d8f-bf92-df7d7dc0faee">
     NdisClOpenAddressFamilyEx</a>.


## -returns



When 
      <b>
      NdisClCloseAddressFamily</b> returns anything other than NDIS_STATUS_PENDING, the client should make
      an internal call to its 
      <a href="https://msdn.microsoft.com/7597e124-34e4-4326-98b3-c65dbe90ae6f">
      ProtocolClCloseAfComplete</a> function. Otherwise, NDIS calls the client's 
      <i>
      ProtocolClCloseAfComplete</i> function when this operation is completed.

If 
      <b>
      NdisClCloseAddressFamily</b> returns NDIS_STATUS_PENDING, a client that is waiting for its 
      <a href="https://msdn.microsoft.com/7597e124-34e4-4326-98b3-c65dbe90ae6f">
      ProtocolClCloseAfComplete</a> function to be called should not block the current thread since this
      could cause a deadlock. This is particularly important when a client calls 
      <b>NdisClCloseAddressFamily</b> in the
      context of handling an 
      <a href="https://msdn.microsoft.com/1967f663-86ce-4e9d-9498-61951bdf4db0">
      NdisCmNotifyCloseAddressFamily</a> request. In this case, the call manager may not close the address
      family until after the client has returned from handling the 
      <b>NdisCmNotifyCloseAddressFamily</b> request. If the client blocks the
      current thread, the client will never complete the handling of the 
      <b>NdisCmNotifyCloseAddressFamily</b> request, thus causing a deadlock.




## -remarks



A client commonly calls 
    <b>NdisClCloseAddressFamily</b> from its    
    <a href="https://msdn.microsoft.com/19fa7be2-acb9-42f6-bd9f-5be3e3c8b5fa">
    ProtocolUnbindAdapterEx</a> function, after it closes all the client's open VCs on the binding with
    calls to 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561627">NdisClCloseCall</a> and/or 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561628">NdisClDeregisterSap</a>. A client can
    also call 
    <b>NdisClCloseAddressFamily</b> in the
    context of processing an 
    <a href="https://msdn.microsoft.com/1967f663-86ce-4e9d-9498-61951bdf4db0">
    NdisCmNotifyCloseAddressFamily</a> request.

NDIS calls a client's 
    <a href="https://msdn.microsoft.com/19fa7be2-acb9-42f6-bd9f-5be3e3c8b5fa">
    ProtocolUnbindAdapterEx</a> function whenever an underlying NIC to which that client is bound is being
    removed from the machine or is being reconfigured. A PnP reconfiguration of the underlying miniport
    driver causes the call manager or MCM driver to reregister the address family it supports over that NIC.
    This, in turn, causes a subsequent call to the client's 
    <a href="https://msdn.microsoft.com/272d99da-ef08-4ebd-90e7-74e99410b3f5">
    ProtocolCoAfRegisterNotify</a> function. In either scenario, the client's 
    <i>
    ProtocolUnbindAdapterEx</i> function must call 
    <b>NdisClCloseAddressFamily</b> with any
    outstanding 
    <i>NdisAfHandle</i> it is currently using that depends on the underlying miniport
    driver.

As a general guideline, a client should release all the resources it allocated for connection-oriented
    communications through the miniport driver before its 
    <a href="https://msdn.microsoft.com/19fa7be2-acb9-42f6-bd9f-5be3e3c8b5fa">
    ProtocolUnbindAdapterEx</a> function calls 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561640">NdisCloseAdapterEx</a>.

The 
    <i>NdisAfHandle</i> passed to 
    <b>NdisClCloseAddressFamily</b> becomes
    invalid for the client as soon as this call occurs.

Before a call to 
    <b>NdisClCloseAddressFamily</b>, the
    client may use the 
    <i>NdisAfHandle</i> while the AF is open or while a 
    <a href="https://msdn.microsoft.com/0f595daa-9822-4ca6-8f25-e6f82030d4ea">
    ProtocolClNotifyCloseAf</a> operation is pending. If the 
    <i>
    ProtocolClNotifyCloseAf</i> function returns NDIS_STATUS_PENDING, use the handle in the 
    <a href="https://msdn.microsoft.com/5d2bbf08-ea5c-4dad-8c30-9a655d25222a">
    NdisClNotifyCloseAddressFamilyComplete</a> call after the close operation completes.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561627">NdisClCloseCall</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561628">NdisClDeregisterSap</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561639">NdisClOpenAddressFamilyEx</a>



<a href="https://msdn.microsoft.com/7597e124-34e4-4326-98b3-c65dbe90ae6f">ProtocolClCloseAfComplete</a>



<a href="https://msdn.microsoft.com/a7a02813-62e4-49c5-abb6-a90f4e092b9f">ProtocolCmCloseAf</a>



<a href="https://msdn.microsoft.com/272d99da-ef08-4ebd-90e7-74e99410b3f5">ProtocolCoAfRegisterNotify</a>



<a href="https://msdn.microsoft.com/19fa7be2-acb9-42f6-bd9f-5be3e3c8b5fa">ProtocolUnbindAdapterEx</a>
 

 

