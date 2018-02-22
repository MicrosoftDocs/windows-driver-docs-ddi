---
UID: NF:ndis.NdisIMDeInitializeDeviceInstance
title: NdisIMDeInitializeDeviceInstance function
author: windows-driver-content
description: The NdisIMDeInitializeDeviceInstance function calls an NDIS intermediate driver's MiniportHaltEx function to tear down the driver's virtual miniport.
old-location: netvista\ndisimdeinitializedeviceinstance.htm
old-project: netvista
ms.assetid: badfab43-ba58-4711-a181-af87dcfeba4d
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: netvista.ndisimdeinitializedeviceinstance, intermediate_ref_6e10d8e6-4dd7-4d92-9c22-949dabac84f9.xml, NdisIMDeInitializeDeviceInstance function [Network Drivers Starting with Windows Vista], NdisIMDeInitializeDeviceInstance, ndis/NdisIMDeInitializeDeviceInstance
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisIMDeInitializeDeviceInstance
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---

# NdisIMDeInitializeDeviceInstance function


## -description


The 
  <b>NdisIMDeInitializeDeviceInstance</b> function calls an NDIS intermediate driver's 
  <a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a> function to tear down the
  driver's virtual miniport.


## -syntax


````
NDIS_STATUS NdisIMDeInitializeDeviceInstance(
  _In_ NDIS_HANDLE NdisMiniportHandle
);
````


## -parameters




### -param NdisMiniportHandle [in]

The handle that NDIS supplied to the 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">
     MiniportInitializeEx</a> function.


## -returns



<b>NdisIMDeInitializeDeviceInstance</b> returns NDIS_STATUS_SUCCESS if the NIC has been torn down.
     Otherwise, it can return NDIS_STATUS_FAILURE if the given 
     <i>NdisMiniportHandle</i> is invalid.




## -remarks



For NDIS intermediate drivers, 
    <b>NdisIMDeInitializeDeviceInstance</b> is the reciprocal of the 
    <a href="..\ndis\nf-ndis-ndisiminitializedeviceinstanceex.md">
    NdisIMInitializeDeviceInstanceEx</a> function. Such a driver usually calls 
    <b>NdisIMDeInitializeDeviceInstance</b> from its 
    <a href="..\ndis\nc-ndis-protocol_unbind_adapter_ex.md">
    ProtocolUnbindAdapterEx</a> function, when the underlying miniport adapter to which it was bound is
    being removed from the system, possibly because it is being reconfigured.

The call to 
    <b>NdisIMDeInitializeDeviceInstance</b> causes an NDIS call to the intermediate driver's 
    <a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a> function after NDIS has
    told all higher level protocol drivers that had bound themselves to the intermediate's virtual miniport
    that they must unbind.




## -see-also

<a href="..\ndis\nf-ndis-ndisiminitializedeviceinstanceex.md">
   NdisIMInitializeDeviceInstanceEx</a>



<a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a>



<a href="..\ndis\nc-ndis-protocol_unbind_adapter_ex.md">ProtocolUnbindAdapterEx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisIMDeInitializeDeviceInstance function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

