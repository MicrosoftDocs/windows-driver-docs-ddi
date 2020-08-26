---
UID: NF:ndis.NdisMGetBusData
title: NdisMGetBusData function (ndis.h)
description: NDIS drivers call the NdisMGetBusData function to read the configuration space of a device.
old-location: netvista\ndismgetbusdata.htm
tech.root: netvista
ms.assetid: 495191f4-a5c6-4223-8c5d-e4c0ecb0cc5d
ms.date: 05/02/2018
keywords: ["NdisMGetBusData function"]
ms.keywords: NdisMGetBusData, NdisMGetBusData function [Network Drivers Starting with Windows Vista], hardware_configuration_ref_e2ffab8c-2dba-4b49-a7dc-246a4792ca43.xml, ndis/NdisMGetBusData, netvista.ndismgetbusdata
f1_keywords:
 - "ndis/NdisMGetBusData"
 - "NdisMGetBusData"
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
- NdisMGetBusData
targetos: Windows
req.typenames: 
---

# NdisMGetBusData function


## -description


NDIS drivers call the 
  <b>NdisMGetBusData</b> function to read the configuration space of a device.


## -parameters




### -param NdisMiniportHandle

The miniport adapter handle that NDIS passed to the 
     <i>MiniportAdapterHandle</i> parameter of the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">
     MiniportInitializeEx</a> function.

### -param WhichSpace 
[in]
The type of bus data to be read. For further information, see the discussion of the 
     <i>WhichSpace</i> parameter on the reference page for 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-read-config">IRP_MN_READ_CONFIG</a>.


### -param Offset 
[in]
The byte offset in the configuration space, specified by 
     <i>WhichSpace</i>, from which data is read.


### -param Buffer 
[out]
A pointer to a buffer that receives the data read from the bus. Must be at least as large as 
     <i>Length</i> .


### -param Length 
[in]
The length, in bytes, of the data to read.


## -returns



<b>NdisMGetBusData</b> returns the number of bytes read.




## -remarks



This function replaces the NDIS 5.1 
    <a href="https://docs.microsoft.com/previous-versions/windows/hardware/network/ff554554(v=vs.85)">NdisReadPciSlotInformation</a> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-read-config">IRP_MN_READ_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsetbusdata">NdisMSetBusData</a>
 

 

