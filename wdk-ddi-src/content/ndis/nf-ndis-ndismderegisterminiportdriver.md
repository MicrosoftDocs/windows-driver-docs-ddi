---
UID: NF:ndis.NdisMDeregisterMiniportDriver
title: NdisMDeregisterMiniportDriver function
author: windows-driver-content
description: A miniport driver calls the NdisMDeregisterMiniportDriver function to release resources that it allocated with a previous call to the NdisMRegisterMiniportDriver function.
old-location: netvista\ndismderegisterminiportdriver.htm
tech.root: netvista
ms.assetid: c428e30d-ce86-4ca0-bc65-45d84a7c910e
ms.date: 5/2/2018
ms.keywords: NdisMDeregisterMiniportDriver, NdisMDeregisterMiniportDriver function [Network Drivers Starting with Windows Vista], miniport_ndis_functions_ref_bd8d7bcd-098a-4367-82d2-6a35753a4a3b.xml, ndis/NdisMDeregisterMiniportDriver, netvista.ndismderegisterminiportdriver
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miniport_Driver_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisMDeregisterMiniportDriver
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMDeregisterMiniportDriver function


## -description


A miniport driver calls the 
  <b>NdisMDeregisterMiniportDriver</b> function to release resources that it allocated with a previous call to
  the 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff563654">NdisMRegisterMiniportDriver</a> function.


## -parameters




### -param NdisMiniportDriverHandle [in]

The handle that the miniport driver obtained in a previous call to 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff563654">NdisMRegisterMiniportDriver</a>.


## -returns



None




## -remarks



If an error occurs in the miniport driver's 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine after the 
    <a href="https://msdn.microsoft.com/bed68aa8-499d-41fd-997b-a46316913cc8">
    NdisMRegisterMiniportDriver</a> function returns successfully, the driver must call 
    <b>NdisMDeregisterMiniportDriver</b> before 
    <b>DriverEntry</b> returns. If 
    <b>DriverEntry</b> succeeds, the driver must call 
    <b>NdisMDeregisterMiniportDriver</b> from its 
    <a href="https://msdn.microsoft.com/25c803cf-f8a6-4e41-a731-c3ae7f1db211">MiniportDriverUnload</a> function.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a>



<a href="https://msdn.microsoft.com/25c803cf-f8a6-4e41-a731-c3ae7f1db211">MiniportDriverUnload</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563654">NdisMRegisterMiniportDriver</a>
 

 

