---
UID: NF:ndis.NdisMDeregisterIoPortRange
title: NdisMDeregisterIoPortRange function
author: windows-driver-content
description: NdisMDeregisterIoPortRange releases a mapping that was set up with NdisMRegisterIoPortRange during driver initialization.
old-location: netvista\ndismderegisterioportrange.htm
old-project: netvista
ms.assetid: b5b6a608-af1f-4030-b83a-a6f64ff3a264
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndismderegisterioportrange, miniport_port_io_ref_3ec72b06-3f52-46b9-b699-774a7df4a658.xml, ndis/NdisMDeregisterIoPortRange, NdisMDeregisterIoPortRange function [Network Drivers Starting with Windows Vista], NdisMDeregisterIoPortRange
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMDeregisterIoPortRange   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMDeregisterIoPortRange   (NDIS 5.1)) in Windows XP.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisMDeregisterIoPortRange
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---

# NdisMDeregisterIoPortRange function


## -description


<b>NdisMDeregisterIoPortRange</b> releases a mapping that was set up with 
  <a href="..\ndis\nf-ndis-ndismregisterioportrange.md">NdisMRegisterIoPortRange</a> during
  driver initialization.


## -syntax


````
VOID NdisMDeregisterIoPortRange(
  _In_ NDIS_HANDLE MiniportAdapterHandle,
  _In_ UINT        InitialPort,
  _In_ UINT        NumberOfPorts,
  _In_ PVOID       PortOffset
);
````


## -parameters




### -param MiniportAdapterHandle [in]

Specifies the handle input to 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>.


### -param InitialPort [in]

Specifies the bus-relative address of the first port in the range of ports.


### -param NumberOfPorts [in]

Specifies the number of ports in the range.


### -param PortOffset [in]

Specifies the mapped base port address returned by 
     <b>NdisMRegisterIoPortRange</b>.


## -returns



None




## -remarks



The miniport driver must pass the same 
    <i>InitialPort</i> and 
    <i>NumberOfPorts</i> to 
    <b>NdisMDeregisterIoPortRange</b> that were passed when 
    <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> called 
    <a href="..\ndis\nf-ndis-ndismregisterioportrange.md">NdisMRegisterIoPortRange</a> to get
    the mapped 
    <i>PortOffset</i> value. That is, a miniport driver cannot call 
    <b>NdisMDeregisterIoPortRange</b> to release a subrange of a mapped port range.

<b>NdisMDeregisterIoPortRange</b> can be called from the 
    <i>MiniportInitializeEx</i> or 
    <a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a> functions only if 
    <i>MiniportInitializeEx</i> previously made a successful call to 
    <b>NdisMRegisterIoPortRange</b>.

<b>NdisMDeregisterIoPortRange</b> also releases the driver's claim on the I/O port range in the
    registry.

After it calls 
    <b>NdisMRegisterIoPortRange</b>, the miniport driver can no longer access the NIC's port range with calls
    to the 
    <b>NdisRaw..Port<i>Xxx</i></b> functions.




## -see-also

<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="..\ndis\nf-ndis-ndismregisterioportrange.md">NdisMRegisterIoPortRange</a>



<a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMDeregisterIoPortRange function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

