---
UID: NF:ndis.NdisIMCancelInitializeDeviceInstance
title: NdisIMCancelInitializeDeviceInstance function
author: windows-driver-content
description: The NdisIMCancelInitializeDeviceInstance function cancels a preceding call to the NdisIMInitializeDeviceInstanceEx function.
old-location: netvista\ndisimcancelinitializedeviceinstance.htm
old-project: netvista
ms.assetid: 809ffee1-b087-4bf0-ba8a-1ac0b2d02f2f
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: NdisIMCancelInitializeDeviceInstance, NdisIMCancelInitializeDeviceInstance function [Network Drivers Starting with Windows Vista], intermediate_ref_4cdce462-8c79-46ad-aa3e-68a0f9b72ef1.xml, ndis/NdisIMCancelInitializeDeviceInstance, netvista.ndisimcancelinitializedeviceinstance
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisIMCancelInitializeDeviceInstance (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers   (see       NdisIMCancelInitializeDeviceInstance (NDIS 5.1)) in Windows XP.
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisIMCancelInitializeDeviceInstance
product: Windows
targetos: Windows
req.typenames: 
---

# NdisIMCancelInitializeDeviceInstance function


## -description


The 
  <b>NdisIMCancelInitializeDeviceInstance</b> function cancels a preceding call to the 
  <a href="https://msdn.microsoft.com/f65c2974-4bf4-4948-ac07-527e69c96303">
  NdisIMInitializeDeviceInstanceEx</a> function.


## -parameters




### -param DriverHandle [in]

The miniport driver handle that the 
     <a href="https://msdn.microsoft.com/bed68aa8-499d-41fd-997b-a46316913cc8">
     NdisMRegisterMiniportDriver</a> function returned at the 
     <i>NdisMiniportDriverHandle</i> parameter.


### -param DeviceInstance [in]

A pointer to an NDIS_STRING type that describes a caller-initialized counted string in the
     system-default character set. The string contains the name of the registry key in which the driver
     stores information about a virtual miniport and, possibly, binding-specific information. For Microsoft
     Windows 2000 and later drivers, this string contains Unicode characters. That is, for Windows 2000 and
     later, NDIS defines the NDIS_STRING type as a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> type.


## -returns



<b>NdisIMCancelInitializeDeviceInstance</b> returns NDIS_STATUS_SUCCESS if it canceled the preceding call
     to 
     <b>NdisIMInitializeDeviceInstanceEx</b>. Otherwise, it returns NDIS_STATUS_FAILURE if there is no way to
     stop the initialization operation for the virtual miniport.




## -remarks



An intermediate driver calls the 
    <a href="https://msdn.microsoft.com/f65c2974-4bf4-4948-ac07-527e69c96303">
    NdisIMInitializeDeviceInstanceEx</a> function to initiate the initialization operation for a virtual
    miniports.Before NDIS calls the driver's 
    <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a> function, the
    driver can call 
    <b>NdisIMCancelInitializeDeviceInstance</b> to cancel the initialization operation. For example, if an
    underlying driver that the intermediate driver requires for normal operation is removed, the intermediate
    driver can cancel the initialization for any virtual miniports that are associated with the removed
    driver.




## -see-also




<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/f65c2974-4bf4-4948-ac07-527e69c96303">
   NdisIMInitializeDeviceInstanceEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563654">NdisMRegisterMiniportDriver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>
 

 

