---
UID: NC:ndis.MINIPORT_INITIALIZE
title: MINIPORT_INITIALIZE (ndis.h)
description: NDIS calls a miniport driver's MiniportInitializeEx function to initialize a miniport adapter for network I/O operations.
old-location: netvista\miniportinitializeex.htm
tech.root: netvista
ms.assetid: b146fa81-005b-4a6c-962d-4cb023ea790e
ms.date: 05/02/2018
keywords: ["MINIPORT_INITIALIZE callback function"]
ms.keywords: MINIPORT_INITIALIZE, MINIPORT_INITIALIZE callback, MiniportInitializeEx, MiniportInitializeEx callback function [Network Drivers Starting with Windows Vista], miniport_functions_ref_d98605bf-4032-4cfe-8529-2d0bebc9e29e.xml, ndis/MiniportInitializeEx, netvista.miniportinitializeex
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - MINIPORT_INITIALIZE
 - ndis/MINIPORT_INITIALIZE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ndis.h
api_name:
 - MiniportInitializeEx
---

# MINIPORT_INITIALIZE callback function


## -description

NDIS calls a miniport driver's
   <i>MiniportInitializeEx</i> function to initialize a miniport adapter for network I/O operations.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_INITIALIZE</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters

### -param NdisMiniportHandle 

[in]
An NDIS-supplied handle that identifies the miniport adapter that the miniport driver should
     initialize.

### -param MiniportDriverContext 

[in]
A handle to a driver-allocated context area where the driver maintains state and configuration
     information. The miniport driver passed this context area to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterminiportdriver">
     NdisMRegisterMiniportDriver</a> function.

### -param MiniportInitParameters 

[in]
A pointer to an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_init_parameters">
     NDIS_MINIPORT_INIT_PARAMETERS</a> structure that defines the initialization parameters for the
     miniport adapter.

## -returns

<i>MiniportInitializeEx</i> can return one of the following status values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
<i>MiniportInitializeEx</i> configured and set up the miniport adapter, and allocated all the resources
       that the driver must have to perform network I/O operations.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_NOT_ACCEPTED</b></dt>
</dl>
</td>
<td width="60%">
<i>MiniportInitializeEx</i> could not get the miniport adapter to accept the configuration parameters
       that 
       <i>MiniportInitializeEx</i> obtained from the registry.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<i>MiniportInitializeEx</i> could not allocate resources to perform network I/O operations. 
       <i>MiniportInitializeEx</i> should call the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiswriteerrorlogentry">NdisWriteErrorLogEntry</a> function
       to identify the resource conflict (for example, I/O port range, interrupt vector, device memory range,
       as appropriate). Supplying an error log record gives the user or system administrator information that
       can be used to reconfigure the computer to avoid such hardware resource conflicts.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>
</td>
<td width="60%">
<i>MiniportInitializeEx</i> failed for reasons other than those in the preceding list. The driver
       should call 
       <b>NdisWriteErrorLogEntry</b> with parameters that specify the reason for the failure.

</td>
</tr>
</table>

## -remarks

NDIS calls 
    <i>MiniportInitializeEx</i> as part of a system PnP operation. Drivers specify the 
    <i>MiniportInitializeEx</i> entry point by calling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterminiportdriver">
    NdisMRegisterMiniportDriver</a> function from the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine. NDIS can call 
    <i>MiniportInitializeEx</i> after 
    <b>DriverEntry</b> returns. For more information, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/initializing-a-miniport-driver">DriverEntry of NDIS
    Miniport Drivers</a>.

For NDIS intermediate drivers, NDIS can call 
    <i>MiniportInitializeEx</i> in the context of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisiminitializedeviceinstanceex">
    NdisIMInitializeDeviceInstanceEx</a> function or after it returns. Such a driver's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_bind_adapter_ex">ProtocolBindAdapterEx</a> function
    usually calls 
    <b>NdisIMInitializeDeviceInstanceEx</b>.

Drivers can register as a combined miniport driver and intermediate driver (see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterminiportdriver">NdisMRegisterMiniportDriver</a>).
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
    <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/ndis-ndisopenconfigurationex">NdisOpenConfigurationEx</a> and 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisreadconfiguration">NdisReadConfiguration</a> functions. The
    driver can call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismgetbusdata">NdisMGetBusData</a> function to obtain
    bus-specific information.

Miniport drivers must call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsetminiportattributes">
    NdisMSetMiniportAttributes</a> function and provide an 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_adapter_registration_attributes">
    NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES</a> structure which contains the following
    attributes:

<ul>
<li>
A handle to a driver-allocated context area.

</li>
<li>
Appropriate attributes flags.

</li>
<li>
The time-out interval for calling its 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_check_for_hang">
      MiniportCheckForHangEx</a> function.

</li>
<li>
The interface type.

</li>
</ul>
The miniport driver passes
    <b>NdisMSetMiniportAttributes</b> a handle at the 
    <b>MiniportAdapterContext</b> member of NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES. The driver
    maintains state information for the specified miniport adapter in this context area. NDIS passes this
    handle as an input parameter to other 
    <i>MiniportXxx</i> functions.

Miniport drivers must set the attributes in the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_adapter_general_attributes">
    NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES</a> structure after they set the registration attributes in
    the NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES structure and before they set any additional
    attributes.

<i>MiniportInitializeEx</i> can also allocate resources such as the following:

<ul>
<li>
Non-paged pool memory

</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a> and 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure pools

</li>
<li>
Spin locks

</li>
<li>
Timers

</li>
<li>
IO ports

</li>
<li>
DMA

</li>
<li>
Shared memory

</li>
<li>
Interrupts

</li>
</ul>
If the driver indicates receives with the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismindicatereceivenetbufferlists">
    NdisMIndicateReceiveNetBufferLists</a> function, the 
    <i>MiniportInitializeEx</i> function should call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferlistpool">
    NdisAllocateNetBufferListPool</a> and 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferpool">
    NdisAllocateNetBufferPool</a> functions and save the handles returned by these NDIS functions.
    Typically, the network data that the driver subsequently indicates with 
    <b>NdisMIndicateReceiveNetBufferLists</b> references structures that were allocated with the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferandnetbufferlist">
    NdisAllocateNetBufferAndNetBufferList</a> function. A driver can also use structures that were
    allocated with the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbuffer">NdisAllocateNetBuffer</a>, and 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferlist">
    NdisAllocateNetBufferList</a> functions.

If driver functions, other than the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_isr">MiniportInterrupt</a> function, share
    resources, 
    <i>MiniportInitializeEx</i> should call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatespinlock">NdisAllocateSpinLock</a> function to set
    up any spin locks necessary to synchronize access to such shared resources. Resources that other driver
    functions share with 
    <i>MiniportInterrupt</i>, such as NIC registers, are protected by the interrupt object that the driver
    set up with the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterinterruptex">
    NdisMRegisterInterruptEx</a> function. Driver functions access these resources by calling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsynchronizewithinterruptex">
    NdisMSynchronizeWithInterruptEx</a> function.

<i>MiniportInitializeEx</i> can call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatetimerobject">NdisAllocateTimerObject</a> function
    with a driver-supplied 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_timer_function">NetTimerCallback</a> function and a pointer
    to driver-allocated memory for a timer object. Drivers can set up multiple 
    <i>NetTimerCallback</i> functions, each with its own timer object. A driver can call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissettimerobject">NdisSetTimerObject</a> function to enable a
    periodic 
    <i>NetTimerCallback</i> function. A driver can also call the 
    <b>NdisSetTimerObject</b> function to enable a one-time 
    <i>NetTimerCallback</i> function.

<i>MiniportInitializeEx</i> must call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsetminiportattributes">
    NdisMSetMiniportAttributes</a> function before it calls any 
    <b>NdisM<i>Xxx</i></b> function, such as the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/ndis-ndismregisterioportrange">NdisMRegisterIoPortRange</a> or 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/ndis-ndismmapiospace">NdisMMapIoSpace</a> functions, that claims
    hardware resources for the miniport adapter. 
    <i>MiniportInitializeEx</i> must call 
    <b>NdisMSetMiniportAttributes</b> before it tries to allocate resources for DMA operations.

If the device supports bus-master DMA, 
    <i>MiniportInitializeEx</i> must call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterscattergatherdma">
    NdisMRegisterScatterGatherDma</a> function after it calls 
    <b>NdisMSetMiniportAttributes</b> and before it calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismallocatesharedmemory">
    NdisMAllocateSharedMemory</a> function. If the device supports subordinate DMA, 
    <i>MiniportInitializeEx</i> must call 
    <b>NdisMSetMiniportAttributes</b> before it calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterdmachannel">
    NdisMRegisterDmaChannel</a> function.

After 
    <i>MiniportInitializeEx</i> calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterinterruptex">
    NdisMRegisterInterruptEx</a> function, NDIS can call the driver's 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_isr">MiniportInterrupt</a> function. NDIS
    calls 
    <i>MiniportInterrupt</i> if the NIC generates an interrupt or if any other device with which the NIC
    shares an interrupt generates an interrupt. Note that a miniport driver can get an interrupt as soon as
    it calls 
    <b>NdisMRegisterInterruptEx</b> and keeps getting interrupts until its call to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismderegisterinterruptex">
    NdisMDeregisterInterruptEx</a> function returns.

<i>MiniportInitializeEx</i> should test the NIC to make sure that the hardware is configured correctly. If
    the driver must wait for state changes to occur in the hardware, 
    <i>MiniportInitializeEx</i> can use the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiswaitevent">NdisWaitEvent</a> function or the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsleep">NdisMSleep</a> function.

After 
    <i>MiniportInitializeEx</i> returns successfully, the miniport adapter is in the 
    <i>Paused</i> state. NDIS can call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_restart">MiniportRestart</a> function to transition the
    miniport adapter to the 
    <i>Running</i> state.

If 
    <i>MiniportInitializeEx</i> returns NDIS_STATUS_SUCCESS, the driver should release all the resources for
    the miniport adapter in the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a> function.

If 
    <i>MiniportInitializeEx</i> failed, 
    <i>MiniportInitializeEx</i> must release all resources that it allocated before it returns and the
    miniport adapter returns to the 
    <i>Halted</i> state.

NDIS calls 
    <i>MiniportInitializeEx</i> at IRQL = PASSIVE_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>MiniportInitializeEx</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>MiniportInitializeEx</i> function that is named "MyInitializeEx", use the <b>MINIPORT_INITIALIZE</b> type as shown in this code example:


```
MINIPORT_INITIALIZE MyInitializeEx;
```

Then, implement your function as follows:


```
_Use_decl_annotations_
NDIS_STATUS
 MyInitializeEx(
    NDIS_HANDLE  NdisMiniportHandle,
    NDIS_HANDLE  MiniportDriverContext,
    PNDIS_MINIPORT_INIT_PARAMETERS  MiniportInitParameters
    )
  {...}
```

The <b>MINIPORT_INITIALIZE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_INITIALIZE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_check_for_hang">MiniportCheckForHangEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_isr">MiniportInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_restart">MiniportRestart</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_adapter_general_attributes">
   NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_adapter_registration_attributes">
   NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_init_parameters">NDIS_MINIPORT_INIT_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer">NET_BUFFER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbuffer">NdisAllocateNetBuffer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferandnetbufferlist">
   NdisAllocateNetBufferAndNetBufferList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferlist">NdisAllocateNetBufferList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferlistpool">
   NdisAllocateNetBufferListPool</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatenetbufferpool">NdisAllocateNetBufferPool</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatespinlock">NdisAllocateSpinLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisallocatetimerobject">NdisAllocateTimerObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismallocatesharedmemory">NdisMAllocateSharedMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismderegisterinterruptex">NdisMDeregisterInterruptEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismgetbusdata">NdisMGetBusData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismindicatereceivenetbufferlists">
   NdisMIndicateReceiveNetBufferLists</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/ndis-ndismmapiospace">NdisMMapIoSpace</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterdmachannel">NdisMRegisterDmaChannel</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterinterruptex">NdisMRegisterInterruptEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/ndis-ndismregisterioportrange">NdisMRegisterIoPortRange</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterminiportdriver">NdisMRegisterMiniportDriver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterscattergatherdma">
   NdisMRegisterScatterGatherDma</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsetminiportattributes">NdisMSetMiniportAttributes</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsleep">NdisMSleep</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsynchronizewithinterruptex">
   NdisMSynchronizeWithInterruptEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/ndis-ndisopenconfigurationex">NdisOpenConfigurationEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisreadconfiguration">NdisReadConfiguration</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndissettimerobject">NdisSetTimerObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiswaitevent">NdisWaitEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiswriteerrorlogentry">NdisWriteErrorLogEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_timer_function">NetTimerCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_bind_adapter_ex">ProtocolBindAdapterEx</a>

