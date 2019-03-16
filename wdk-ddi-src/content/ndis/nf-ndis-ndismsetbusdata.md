---
UID: NF:ndis.NdisMSetBusData
title: NdisMSetBusData function (ndis.h)
description: NDIS drivers call the NdisMSetBusData function to write to the configuration space of a device.
old-location: netvista\ndismsetbusdata.htm
tech.root: netvista
ms.assetid: 0b9153b3-f379-40c4-87f6-1fa380070e65
ms.date: 05/02/2018
ms.keywords: NdisMSetBusData, NdisMSetBusData function [Network Drivers Starting with Windows Vista], hardware_configuration_ref_4fd9608c-60b9-4a86-9aa3-02d6ec17da92.xml, ndis/NdisMSetBusData, netvista.ndismsetbusdata
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
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
req.lib: Ndis.lib
req.dll: 
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisMSetBusData
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMSetBusData function


## -description


NDIS drivers call the 
  <b>NdisMSetBusData</b> function to write to the configuration space of a device.


## -parameters




### -param NdisMiniportHandle

The miniport adapter handle that NDIS passed to the 
     <i>MiniportAdapterHandle</i> parameter of the 
     <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">
     MiniportInitializeEx</a> function.

### -param WhichSpace [in]

The type of bus data to be written. For further information, see the discussion of the 
     <i>WhichSpace</i> parameter on the reference page for 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff551727">IRP_MN_READ_CONFIG</a>.


### -param Offset [in]

The byte offset in the configuration space, specified by 
     <i>WhichSpace</i>, to which data is written.


### -param Buffer [in]

A pointer to a buffer that contains the data to write to the bus. Must be at least as large as 
     <i>Length</i> .


### -param Length [in]

The length, in bytes, of the data to write.


## -returns



<b>NdisMGetBusData</b> returns the number of bytes written.




## -remarks



This function replaces the NDIS 5.1 
    <a href="https://msdn.microsoft.com/6783ad54-3382-456b-a59e-3fc2b1f91cd6">
    NdisWritePciSlotInformation</a> function.






## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551727">IRP_MN_READ_CONFIG</a>



<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563591">NdisMGetBusData</a>
 

 

