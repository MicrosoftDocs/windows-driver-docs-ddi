---
UID: NF:ndis.NdisDeregisterDeviceEx
title: NdisDeregisterDeviceEx function
author: windows-driver-content
description: The NdisDeregisterDeviceEx function removes, from the system, a device object that was created by the NdisRegisterDeviceEx function.
old-location: netvista\ndisderegisterdeviceex.htm
tech.root: netvista
ms.assetid: bca1ef90-b574-4ed5-a9ec-c553372490b1
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: NdisDeregisterDeviceEx, NdisDeregisterDeviceEx function [Network Drivers Starting with Windows Vista], ndis/NdisDeregisterDeviceEx, ndis_devices_ref_40ed1b6b-39ce-43fc-ae0d-8371eab300d7.xml, netvista.ndisderegisterdeviceex
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisDeregisterDeviceEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisDeregisterDeviceEx function


## -description


The 
  <b>NdisDeregisterDeviceEx</b> function removes, from the system, a device object that was created by the 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff564518">NdisRegisterDeviceEx</a> function.


## -parameters




### -param NdisDeviceHandle [in]

The handle returned by 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff564518">NdisRegisterDeviceEx</a> that identifies
     the device object to be deregistered.


## -returns



None




## -remarks



The 
    <b>NdisDeregisterDeviceEx</b> function removes a device object that was created by the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564518">NdisRegisterDeviceEx</a> function. 
    <b>NdisDeregisterDeviceEx</b> also removes the symbolic link that is associated with this device
    object.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564518">NdisRegisterDeviceEx</a>
 

 

