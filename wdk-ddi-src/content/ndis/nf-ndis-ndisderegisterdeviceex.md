---
UID: NF:ndis.NdisDeregisterDeviceEx
title: NdisDeregisterDeviceEx function (ndis.h)
description: The NdisDeregisterDeviceEx function removes, from the system, a device object that was created by the NdisRegisterDeviceEx function.
old-location: netvista\ndisderegisterdeviceex.htm
tech.root: netvista
ms.assetid: bca1ef90-b574-4ed5-a9ec-c553372490b1
ms.date: 05/02/2018
keywords: ["NdisDeregisterDeviceEx function"]
ms.keywords: NdisDeregisterDeviceEx, NdisDeregisterDeviceEx function [Network Drivers Starting with Windows Vista], ndis/NdisDeregisterDeviceEx, ndis_devices_ref_40ed1b6b-39ce-43fc-ae0d-8371eab300d7.xml, netvista.ndisderegisterdeviceex
f1_keywords:
 - "ndis/NdisDeregisterDeviceEx"
 - "NdisDeregisterDeviceEx"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miscellaneous_Function
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
- NdisDeregisterDeviceEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisDeregisterDeviceEx function


## -description


The 
  <b>NdisDeregisterDeviceEx</b> function removes, from the system, a device object that was created by the 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisregisterdeviceex">NdisRegisterDeviceEx</a> function.


## -parameters




### -param NdisDeviceHandle [in]

The handle returned by 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisregisterdeviceex">NdisRegisterDeviceEx</a> that identifies
     the device object to be deregistered.


## -remarks



The 
    <b>NdisDeregisterDeviceEx</b> function removes a device object that was created by the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisregisterdeviceex">NdisRegisterDeviceEx</a> function. 
    <b>NdisDeregisterDeviceEx</b> also removes the symbolic link that is associated with this device
    object.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisregisterdeviceex">NdisRegisterDeviceEx</a>
 

 

