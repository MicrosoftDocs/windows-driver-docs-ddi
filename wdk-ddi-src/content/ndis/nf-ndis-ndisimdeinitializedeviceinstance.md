---
UID: NF:ndis.NdisIMDeInitializeDeviceInstance
title: NdisIMDeInitializeDeviceInstance function (ndis.h)
description: The NdisIMDeInitializeDeviceInstance function calls an NDIS intermediate driver's MiniportHaltEx function to tear down the driver's virtual miniport.
old-location: netvista\ndisimdeinitializedeviceinstance.htm
tech.root: netvista
ms.assetid: badfab43-ba58-4711-a181-af87dcfeba4d
ms.date: 05/02/2018
ms.keywords: NdisIMDeInitializeDeviceInstance, NdisIMDeInitializeDeviceInstance function [Network Drivers Starting with Windows Vista], intermediate_ref_6e10d8e6-4dd7-4d92-9c22-949dabac84f9.xml, ndis/NdisIMDeInitializeDeviceInstance, netvista.ndisimdeinitializedeviceinstance
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisIMDeInitializeDeviceInstance (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       NdisIMDeInitializeDeviceInstance (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_IM_Function
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisIMDeInitializeDeviceInstance
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisIMDeInitializeDeviceInstance function


## -description


The 
  <b>NdisIMDeInitializeDeviceInstance</b> function calls an NDIS intermediate driver's 
  <a href="https://msdn.microsoft.com/b8d452b4-bef3-4991-87cf-fac15bedfde4">MiniportHaltEx</a> function to tear down the
  driver's virtual miniport.


## -parameters




### -param NdisMiniportHandle [in]

The handle that NDIS supplied to the 
     <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">
     MiniportInitializeEx</a> function.


## -returns



<b>NdisIMDeInitializeDeviceInstance</b> returns NDIS_STATUS_SUCCESS if the NIC has been torn down.
     Otherwise, it can return NDIS_STATUS_FAILURE if the given 
     <i>NdisMiniportHandle</i> is invalid.




## -remarks



For NDIS intermediate drivers, 
    <b>NdisIMDeInitializeDeviceInstance</b> is the reciprocal of the 
    <a href="https://msdn.microsoft.com/f65c2974-4bf4-4948-ac07-527e69c96303">
    NdisIMInitializeDeviceInstanceEx</a> function. Such a driver usually calls 
    <b>NdisIMDeInitializeDeviceInstance</b> from its 
    <a href="https://msdn.microsoft.com/19fa7be2-acb9-42f6-bd9f-5be3e3c8b5fa">
    ProtocolUnbindAdapterEx</a> function, when the underlying miniport adapter to which it was bound is
    being removed from the system, possibly because it is being reconfigured.

The call to 
    <b>NdisIMDeInitializeDeviceInstance</b> causes an NDIS call to the intermediate driver's 
    <a href="https://msdn.microsoft.com/b8d452b4-bef3-4991-87cf-fac15bedfde4">MiniportHaltEx</a> function after NDIS has
    told all higher level protocol drivers that had bound themselves to the intermediate's virtual miniport
    that they must unbind.




## -see-also




<a href="https://msdn.microsoft.com/b8d452b4-bef3-4991-87cf-fac15bedfde4">MiniportHaltEx</a>



<a href="https://msdn.microsoft.com/f65c2974-4bf4-4948-ac07-527e69c96303">
   NdisIMInitializeDeviceInstanceEx</a>



<a href="https://msdn.microsoft.com/19fa7be2-acb9-42f6-bd9f-5be3e3c8b5fa">ProtocolUnbindAdapterEx</a>
 

 

