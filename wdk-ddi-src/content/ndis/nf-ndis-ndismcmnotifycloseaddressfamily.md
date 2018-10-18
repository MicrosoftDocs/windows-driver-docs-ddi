---
UID: NF:ndis.NdisMCmNotifyCloseAddressFamily
title: NdisMCmNotifyCloseAddressFamily macro
author: windows-driver-content
description: The NdisMCmNotifyCloseAddressFamily function notifies NDIS that a specified address family (AF) that is associated with a miniport call manager (MCM) should be closed and NDIS should notify any affected CoNDIS clients.
old-location: netvista\ndismcmnotifycloseaddressfamily.htm
tech.root: netvista
ms.assetid: 47b0b1da-e29b-45cc-921b-69d630670b44
ms.date: 5/2/2018
ms.keywords: NdisMCmNotifyCloseAddressFamily, NdisMCmNotifyCloseAddressFamily macro [Network Drivers Starting with Windows Vista], condis_mcm_ref_448486f3-1eeb-4f45-b764-6fd4ab06b63e.xml, ndis/NdisMCmNotifyCloseAddressFamily, netvista.ndismcmnotifycloseaddressfamily
ms.topic: macro
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NdisMCmNotifyCloseAddressFamily
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMCmNotifyCloseAddressFamily macro


## -description


The 
  <b>NdisMCmNotifyCloseAddressFamily</b> function notifies NDIS that a specified address family (AF) that is
  associated with a miniport call manager (MCM) should be closed and NDIS should notify any affected CoNDIS
  clients.


## -parameters




### -param _AH_

A handle that identifies the AF that NDIS should close. NDIS supplied this handle to the MCM's 
     <a href="https://msdn.microsoft.com/7422c205-bc41-4121-b430-ff9e6b49dc2e">ProtocolCmOpenAf</a> function.

## -remarks



MCMs, which register as NDIS miniport drivers by calling the 
    <a href="https://msdn.microsoft.com/bed68aa8-499d-41fd-997b-a46316913cc8">
    NdisMRegisterMiniportDriver</a> function, can call the 
    <b>NdisMCmNotifyCloseAddressFamily</b> function. Stand-alone call managers instead call the 
    <a href="https://msdn.microsoft.com/1967f663-86ce-4e9d-9498-61951bdf4db0">
    NdisCmNotifyCloseAddressFamily</a> function.

To close an AF for a miniport adapter, the MCM should call 
    <b>NdisMCmNotifyCloseAddressFamily</b> from its 
    <a href="https://msdn.microsoft.com/b8d452b4-bef3-4991-87cf-fac15bedfde4">MiniportHaltEx</a> function. NDIS
    subsequently calls the 
    <a href="https://msdn.microsoft.com/0f595daa-9822-4ca6-8f25-e6f82030d4ea">
    ProtocolClNotifyCloseAf</a> function of the client that has the specified AF open.

If 
    <b>NdisMCmNotifyCloseAddressFamily</b> returns NDIS_STATUS_PENDING, NDIS calls the MCM's 
    <a href="https://msdn.microsoft.com/c5bdedee-dacd-4f4d-a3d1-f1cb71a68001">
    ProtocolCmNotifyCloseAfComplete</a> function after the client completes the AF close operation.




## -see-also




<a href="https://msdn.microsoft.com/b8d452b4-bef3-4991-87cf-fac15bedfde4">MiniportHaltEx</a>



<a href="https://msdn.microsoft.com/1967f663-86ce-4e9d-9498-61951bdf4db0">
   NdisCmNotifyCloseAddressFamily</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563654">NdisMRegisterMiniportDriver</a>



<a href="https://msdn.microsoft.com/0f595daa-9822-4ca6-8f25-e6f82030d4ea">ProtocolClNotifyCloseAf</a>



<a href="https://msdn.microsoft.com/c5bdedee-dacd-4f4d-a3d1-f1cb71a68001">
   ProtocolCmNotifyCloseAfComplete</a>



<a href="https://msdn.microsoft.com/7422c205-bc41-4121-b430-ff9e6b49dc2e">ProtocolCmOpenAf</a>
 

 

