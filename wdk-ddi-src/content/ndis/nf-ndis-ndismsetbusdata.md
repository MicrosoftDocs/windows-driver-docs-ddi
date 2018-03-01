---
UID: NF:ndis.NdisMSetBusData
title: NdisMSetBusData function
author: windows-driver-content
description: NDIS drivers call the NdisMSetBusData function to write to the configuration space of a device.
old-location: netvista\ndismsetbusdata.htm
old-project: netvista
ms.assetid: 0b9153b3-f379-40c4-87f6-1fa380070e65
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisMSetBusData, NdisMSetBusData function [Network Drivers Starting with Windows Vista], hardware_configuration_ref_4fd9608c-60b9-4a86-9aa3-02d6ec17da92.xml, ndis/NdisMSetBusData, netvista.ndismsetbusdata
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisMSetBusData
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisMSetBusData function


## -description


NDIS drivers call the 
  <b>NdisMSetBusData</b> function to write to the configuration space of a device.


## -syntax


````
ULONG NdisMSetBusData(
  _In_ NDIS_HANDLE MiniportAdapterHandle,
  _In_ ULONG       WhichSpace,
  _In_ ULONG       Offset,
  _In_ PVOID       Buffer,
  _In_ ULONG       Length
);
````


## -parameters




### -param NdisMiniportHandle

TBD


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


#### - MiniportAdapterHandle [in]

The miniport adapter handle that NDIS passed to the 
     <i>MiniportAdapterHandle</i> parameter of the 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">
     MiniportInitializeEx</a> function.


## -returns



<b>NdisMGetBusData</b> returns the number of bytes written.




## -remarks



This function replaces the NDIS 5.1 
    <a href="https://msdn.microsoft.com/6783ad54-3382-456b-a59e-3fc2b1f91cd6">
    NdisWritePciSlotInformation</a> function.






## -see-also

<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="..\ndis\nf-ndis-ndismgetbusdata.md">NdisMGetBusData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551727">IRP_MN_READ_CONFIG</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMSetBusData function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

