---
UID: NF:ndis.NdisMGetBusData
title: NdisMGetBusData function
author: windows-driver-content
description: NDIS drivers call the NdisMGetBusData function to read the configuration space of a device.
old-location: netvista\ndismgetbusdata.htm
old-project: netvista
ms.assetid: 495191f4-a5c6-4223-8c5d-e4c0ecb0cc5d
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , B, D, G, M, N, NdisMGetBusData, NdisMGetBusData function [Network Drivers Starting with Windows Vista], a, d, e, hardware_configuration_ref_e2ffab8c-2dba-4b49-a7dc-246a4792ca43.xml, i, ndis/NdisMGetBusData, netvista.ndismgetbusdata, s, t, u"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisMGetBusData
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisMGetBusData function


## -description


NDIS drivers call the 
  <b>NdisMGetBusData</b> function to read the configuration space of a device.


## -syntax


````
ULONG NdisMGetBusData(
  _In_  NDIS_HANDLE MiniportAdapterHandle,
  _In_  ULONG       WhichSpace,
  _In_  ULONG       Offset,
  _Out_ PVOID       Buffer,
  _In_  ULONG       Length
);
````


## -parameters




### -param NdisMiniportHandle

TBD


### -param WhichSpace [in]

The type of bus data to be read. For further information, see the discussion of the 
     <i>WhichSpace</i> parameter on the reference page for 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff551727">IRP_MN_READ_CONFIG</a>.


### -param Offset [in]

The byte offset in the configuration space, specified by 
     <i>WhichSpace</i>, from which data is read.


### -param Buffer [out]

A pointer to a buffer that receives the data read from the bus. Must be at least as large as 
     <i>Length</i> .


### -param Length [in]

The length, in bytes, of the data to read.


#### - MiniportAdapterHandle [in]

The miniport adapter handle that NDIS passed to the 
     <i>MiniportAdapterHandle</i> parameter of the 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">
     MiniportInitializeEx</a> function.


## -returns



<b>NdisMGetBusData</b> returns the number of bytes read.




## -remarks



This function replaces the NDIS 5.1 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff554554">NdisReadPciSlotInformation</a> function.




## -see-also

<a href="..\ndis\nf-ndis-ndismsetbusdata.md">NdisMSetBusData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551727">IRP_MN_READ_CONFIG</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMGetBusData function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

