---
UID: NC:ndis.MINIPORT_INITIALIZE
title: MINIPORT_INITIALIZE
author: windows-driver-content
description: NDIS calls a miniport driver's MiniportInitializeEx function to initialize a miniport adapter for network I/O operations.
old-location: netvista\miniportinitializeex.htm
old-project: netvista
ms.assetid: b146fa81-005b-4a6c-962d-4cb023ea790e
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RxNameCacheInitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MiniportInitializeEx
req.alt-loc: Ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# MINIPORT_INITIALIZE callback



## -description
NDIS calls a miniport driver's
   <i>MiniportInitializeEx</i> function to initialize a miniport adapter for network I/O operations.



## -prototype

````
MINIPORT_INITIALIZE MiniportInitializeEx;

NDIS_STATUS MiniportInitializeEx(
  _In_ NDIS_HANDLE                    NdisMiniportHandle,
  _In_ NDIS_HANDLE                    MiniportDriverContext,
  _In_ PNDIS_MINIPORT_INIT_PARAMETERS MiniportInitParameters
)
{ ... }
````


## -parameters

### -param NdisMiniportHandle [in]

An NDIS-supplied handle that identifies the miniport adapter that the miniport driver should
     initialize.


### -param MiniportDriverContext [in]

A handle to a driver-allocated context area where the driver maintains state and configuration
     information. The miniport driver passed this context area to the 
     <a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">
     NdisMRegisterMiniportDriver</a> function.


### -param MiniportInitParameters [in]

A pointer to an 
     <a href="..\ndis\ns-ndis-_ndis_miniport_init_parameters.md">
     NDIS_MINIPORT_INIT_PARAMETERS</a> structure that defines the initialization parameters for the
     miniport adapter.


## -returns
<i>MiniportInitializeEx</i> can return one of the following status values:
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl><i>MiniportInitializeEx</i> configured and set up the miniport adapter, and allocated all the resources
       that the driver must have to perform network I/O operations.
<dl>
<dt><b>NDIS_STATUS_NOT_ACCEPTED</b></dt>
</dl><i>MiniportInitializeEx</i> could not get the miniport adapter to accept the configuration parameters
       that 
       <i>MiniportInitializeEx</i> obtained from the registry.
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl><i>MiniportInitializeEx</i> could not allocate resources to perform network I/O operations. 
       <i>MiniportInitializeEx</i> should call the 
       <a href="..\ndis\nf-ndis-ndiswriteerrorlogentry.md">NdisWriteErrorLogEntry</a> function
       to identify the resource conflict (for example, I/O port range, interrupt vector, device memory range,
       as appropriate). Supplying an error log record gives the user or system administrator information that
       can be used to reconfigure the computer to avoid such hardware resource conflicts.
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl><i>MiniportInitializeEx</i> failed for reasons other than those in the preceding list. The driver
       should call 
       <b>NdisWriteErrorLogEntry</b> with parameters that specify the reason for the failure.

 


## -remarks
NDIS calls 
    <i>MiniportInitializeEx</i> as part of a system PnP operation. Drivers specify the 
    <i>MiniportInitializeEx</i> entry point by calling the 
    <a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">
    NdisMRegisterMiniportDriver</a> function from the 
    <a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a> routine. NDIS can call 
    <i>MiniportInitializeEx</i> after 
    <b>DriverEntry</b> returns. For more information, see 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff548818">DriverEntry of NDIS
    Miniport Drivers</a>.

For NDIS intermediate drivers, NDIS can call 
    <i>MiniportInitializeEx</i> in the context of the 
    <a href="..\ndis\nf-ndis-ndisiminitializedeviceinstanceex.md">
    NdisIMInitializeDeviceInstanceEx</a> function or after it returns. Such a driver's 
    <a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a> function
    usually calls 
    <b>NdisIMInitializeDeviceInstanceEx</b>.

Drivers can register as a combined miniport driver and intermediate driver (see 
    <a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">NdisMRegisterMiniportDriver</a>).
    Such a miniport-intermediate driver functions similarly to an intermediate driver layered over a physical
    miniport driver. For each virtual or physical device instance of a miniport-intermediate driver, if the 
    <b>IMMiniport</b> registry key is set to 
    <b>DWORD:0x0000001</b>, NDIS calls the 
    <i>MiniportInitializeEx</i> function that the driver registered for the virtual device. Otherwise, NDIS
    calls the driver's 
    <i>MiniportInitializeEx</i> function that the driver registered for the physical device.

Until 
    <i>MiniportInitializeEx</i> returns, NDIS submits no requests for the miniport adapter being initialized.
    The miniport adapter is in the 
    <i>initializing</i> state.

To obtain configuration information for the miniport adapter, a driver calls the 
    <a href="..\ndis\nf-ndis-ndisopenconfigurationex.md">NdisOpenConfigurationEx</a> and 
    <a href="..\ndis\nf-ndis-ndisreadconfiguration.md">NdisReadConfiguration</a> functions. The
    driver can call the 
    <a href="..\ndis\nf-ndis-ndismgetbusdata.md">NdisMGetBusData</a> function to obtain
    bus-specific information.

Miniport drivers must call the 
    <a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">
    NdisMSetMiniportAttributes</a> function and provide an 
    <a href="..\ndis\ns-ndis-_ndis_miniport_adapter_registration_attributes.md">
    NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES</a> structure which contains the following
    attributes:

A handle to a driver-allocated context area.

Appropriate attributes flags.

The time-out interval for calling its 
      <a href="..\ndis\nc-ndis-miniport_check_for_hang.md">
      MiniportCheckForHangEx</a> function.

The interface type.

The miniport driver passes
    <b>NdisMSetMiniportAttributes</b> a handle at the 
    <b>MiniportAdapterContext</b> member of NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES. The driver
    maintains state information for the specified miniport adapter in this context area. NDIS passes this
    handle as an input parameter to other 
    <i>MiniportXxx</i> functions.

Miniport drivers must set the attributes in the 
    <a href="..\ndis\ns-ndis-_ndis_miniport_adapter_general_attributes.md">
    NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES</a> structure after they set the registration attributes in
    the NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES structure and before they set any additional
    attributes.

<i>MiniportInitializeEx</i> can also allocate resources such as the following:

Non-paged pool memory


<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> and 
      <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure pools

Spin locks

Timers

IO ports

DMA

Shared memory

Interrupts

If the driver indicates receives with the 
    <a href="..\ndis\nf-ndis-ndismindicatereceivenetbufferlists.md">
    NdisMIndicateReceiveNetBufferLists</a> function, the 
    <i>MiniportInitializeEx</i> function should call the 
    <a href="..\ndis\nf-ndis-ndisallocatenetbufferlistpool.md">
    NdisAllocateNetBufferListPool</a> and 
    <a href="..\ndis\nf-ndis-ndisallocatenetbufferpool.md">
    NdisAllocateNetBufferPool</a> functions and save the handles returned by these NDIS functions.
    Typically, the network data that the driver subsequently indicates with 
    <b>NdisMIndicateReceiveNetBufferLists</b> references structures that were allocated with the 
    <a href="..\ndis\nf-ndis-ndisallocatenetbufferandnetbufferlist.md">
    NdisAllocateNetBufferAndNetBufferList</a> function. A driver can also use structures that were
    allocated with the 
    <a href="..\ndis\nf-ndis-ndisallocatenetbuffer.md">NdisAllocateNetBuffer</a>, and 
    <a href="..\ndis\nf-ndis-ndisallocatenetbufferlist.md">
    NdisAllocateNetBufferList</a> functions.

If driver functions, other than the 
    <a href="..\ndis\nc-ndis-miniport_isr.md">MiniportInterrupt</a> function, share
    resources, 
    <i>MiniportInitializeEx</i> should call the 
    <a href="..\ndis\nf-ndis-ndisallocatespinlock.md">NdisAllocateSpinLock</a> function to set
    up any spin locks necessary to synchronize access to such shared resources. Resources that other driver
    functions share with 
    <i>MiniportInterrupt</i>, such as NIC registers, are protected by the interrupt object that the driver
    set up with the 
    <a href="..\ndis\nf-ndis-ndismregisterinterruptex.md">
    NdisMRegisterInterruptEx</a> function. Driver functions access these resources by calling the 
    <a href="..\ndis\nf-ndis-ndismsynchronizewithinterruptex.md">
    NdisMSynchronizeWithInterruptEx</a> function.

<i>MiniportInitializeEx</i> can call the 
    <a href="..\ndis\nf-ndis-ndisallocatetimerobject.md">NdisAllocateTimerObject</a> function
    with a driver-supplied 
    <a href="..\ndis\nc-ndis-ndis_timer_function.md">NetTimerCallback</a> function and a pointer
    to driver-allocated memory for a timer object. Drivers can set up multiple 
    <i>NetTimerCallback</i> functions, each with its own timer object. A driver can call the 
    <a href="..\ndis\nf-ndis-ndissettimerobject.md">NdisSetTimerObject</a> function to enable a
    periodic 
    <i>NetTimerCallback</i> function. A driver can also call the 
    <b>NdisSetTimerObject</b> function to enable a one-time 
    <i>NetTimerCallback</i> function.

<i>MiniportInitializeEx</i> must call the 
    <a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">
    NdisMSetMiniportAttributes</a> function before it calls any 
    <b>NdisM<i>Xxx</i></b> function, such as the 
    <a href="..\ndis\nf-ndis-ndismregisterioportrange.md">NdisMRegisterIoPortRange</a> or 
    <a href="..\ndis\nf-ndis-ndismmapiospace.md">NdisMMapIoSpace</a> functions, that claims
    hardware resources for the miniport adapter. 
    <i>MiniportInitializeEx</i> must call 
    <b>NdisMSetMiniportAttributes</b> before it tries to allocate resources for DMA operations.

If the device supports bus-master DMA, 
    <i>MiniportInitializeEx</i> must call the 
    <a href="..\ndis\nf-ndis-ndismregisterscattergatherdma.md">
    NdisMRegisterScatterGatherDma</a> function after it calls 
    <b>NdisMSetMiniportAttributes</b> and before it calls the 
    <a href="..\ndis\nf-ndis-ndismallocatesharedmemory.md">
    NdisMAllocateSharedMemory</a> function. If the device supports subordinate DMA, 
    <i>MiniportInitializeEx</i> must call 
    <b>NdisMSetMiniportAttributes</b> before it calls the 
    <a href="..\ndis\nf-ndis-ndismregisterdmachannel.md">
    NdisMRegisterDmaChannel</a> function.

After 
    <i>MiniportInitializeEx</i> calls the 
    <a href="..\ndis\nf-ndis-ndismregisterinterruptex.md">
    NdisMRegisterInterruptEx</a> function, NDIS can call the driver's 
    <a href="..\ndis\nc-ndis-miniport_isr.md">MiniportInterrupt</a> function. NDIS
    calls 
    <i>MiniportInterrupt</i> if the NIC generates an interrupt or if any other device with which the NIC
    shares an interrupt generates an interrupt. Note that a miniport driver can get an interrupt as soon as
    it calls 
    <b>NdisMRegisterInterruptEx</b> and keeps getting interrupts until its call to the 
    <a href="..\ndis\nf-ndis-ndismderegisterinterruptex.md">
    NdisMDeregisterInterruptEx</a> function returns.

<i>MiniportInitializeEx</i> should test the NIC to make sure that the hardware is configured correctly. If
    the driver must wait for state changes to occur in the hardware, 
    <i>MiniportInitializeEx</i> can use the 
    <a href="..\ndis\nf-ndis-ndiswaitevent.md">NdisWaitEvent</a> function or the 
    <a href="..\ndis\nf-ndis-ndismsleep.md">NdisMSleep</a> function.

After 
    <i>MiniportInitializeEx</i> returns successfully, the miniport adapter is in the 
    <i>Paused</i> state. NDIS can call the 
    <a href="..\ndis\nc-ndis-miniport_restart.md">MiniportRestart</a> function to transition the
    miniport adapter to the 
    <i>Running</i> state.

If 
    <i>MiniportInitializeEx</i> returns NDIS_STATUS_SUCCESS, the driver should release all the resources for
    the miniport adapter in the 
    <a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a> function.

If 
    <i>MiniportInitializeEx</i> failed, 
    <i>MiniportInitializeEx</i> must release all resources that it allocated before it returns and the
    miniport adapter returns to the 
    <i>Halted</i> state.

NDIS calls 
    <i>MiniportInitializeEx</i> at IRQL = PASSIVE_LEVEL.

To define a <i>MiniportInitializeEx</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>MiniportInitializeEx</i> function that is named "MyInitializeEx", use the <b>MINIPORT_INITIALIZE</b> type as shown in this code example:

Then, implement your function as follows:

The <b>MINIPORT_INITIALIZE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_INITIALIZE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 


## -see-also
<dl>
<dt>
<a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_check_for_hang.md">MiniportCheckForHangEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_isr.md">MiniportInterrupt</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_restart.md">MiniportRestart</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_ndis_miniport_adapter_general_attributes.md">
   NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_ndis_miniport_adapter_registration_attributes.md">
   NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_ndis_miniport_init_parameters.md">NDIS_MINIPORT_INIT_PARAMETERS</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisallocatenetbuffer.md">NdisAllocateNetBuffer</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisallocatenetbufferlist.md">NdisAllocateNetBufferList</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisallocatenetbufferlistpool.md">
   NdisAllocateNetBufferListPool</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisallocatenetbufferandnetbufferlist.md">
   NdisAllocateNetBufferAndNetBufferList</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisallocatenetbufferpool.md">NdisAllocateNetBufferPool</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisallocatespinlock.md">NdisAllocateSpinLock</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisallocatetimerobject.md">NdisAllocateTimerObject</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismallocatesharedmemory.md">NdisMAllocateSharedMemory</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismderegisterinterruptex.md">NdisMDeregisterInterruptEx</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismindicatereceivenetbufferlists.md">
   NdisMIndicateReceiveNetBufferLists</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismgetbusdata.md">NdisMGetBusData</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismmapiospace.md">NdisMMapIoSpace</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismregisterdmachannel.md">NdisMRegisterDmaChannel</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismregisterinterruptex.md">NdisMRegisterInterruptEx</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismregisterioportrange.md">NdisMRegisterIoPortRange</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">NdisMRegisterMiniportDriver</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismregisterscattergatherdma.md">
   NdisMRegisterScatterGatherDma</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">NdisMSetMiniportAttributes</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismsleep.md">NdisMSleep</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismsynchronizewithinterruptex.md">
   NdisMSynchronizeWithInterruptEx</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisopenconfigurationex.md">NdisOpenConfigurationEx</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisreadconfiguration.md">NdisReadConfiguration</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndissettimerobject.md">NdisSetTimerObject</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiswaitevent.md">NdisWaitEvent</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiswriteerrorlogentry.md">NdisWriteErrorLogEntry</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-ndis_timer_function.md">NetTimerCallback</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_INITIALIZE callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

