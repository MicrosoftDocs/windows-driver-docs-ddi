---
UID: NC:ndis.MINIPORT_HALT
title: MINIPORT_HALT
author: windows-driver-content
description: NDIS calls a miniport driver's MiniportHaltEx function to free resources when a miniport adapter is removed, and to stop the hardware.
old-location: netvista\miniporthaltex.htm
old-project: netvista
ms.assetid: b8d452b4-bef3-4991-87cf-fac15bedfde4
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: MINIPORT_HALT, MiniportHaltEx, MiniportHaltEx callback function [Network Drivers Starting with Windows Vista], miniport_functions_ref_aa826b59-f204-43ea-81b6-f1bab84a7a23.xml, ndis/MiniportHaltEx, netvista.miniporthaltex
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
req.ddi-compliance: WlanAssociation, WlanConnectionRoaming, WlanDisassociation, WlanTimedAssociation, WlanTimedConnectionRoaming, WlanTimedConnectRequest, WlanTimedLinkQuality, WlanTimedScan
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ndis.h
api_name:
-	MiniportHaltEx
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# MINIPORT_HALT callback


## -description


NDIS calls a miniport driver's 
   <i>MiniportHaltEx</i> function to free resources when a miniport adapter is
   removed, and to stop the hardware. This function puts the miniport into the Halted state, where no other callback can occur (including <a href="..\ndis\nc-ndis-miniport_shutdown.md">MiniportShutdownEx</a>). For more information about miniport driver states, see <a href="https://msdn.microsoft.com/b47e2cbe-9da3-4600-9afe-b082e60b87fb">Miniport Adapter States and Operations</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_HALT</b> type. For more information,
   see the following Examples section.</div><div> </div>

## -prototype


````
MINIPORT_HALT MiniportHaltEx;

VOID MiniportHaltEx(
  _In_ NDIS_HANDLE      MiniportAdapterContext,
  _In_ NDIS_HALT_ACTION HaltAction
)
{ ... }
````


## -parameters




### -param MiniportAdapterContext [in]

A handle to a context area that the miniport driver allocated in its 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function.
     The miniport driver uses this context area to maintain state information for a miniport adapter.


### -param HaltAction [in]

The reason for halting the miniport adapter. It can be one of the following values:
     





#### NdisHaltDeviceDisabled

NDIS is halting the miniport adapter in response to a Plug and Play (PnP) remove message.



#### NdisHaltDeviceInstanceDeInitialized

NDIS is halting the miniport adapter in response to an intermediate driver calling the 
       <a href="..\ndis\nf-ndis-ndisimdeinitializedeviceinstance.md">
       NdisIMDeInitializeDeviceInstance</a> function.



#### NdisHaltDevicePoweredDown

NDIS is halting the miniport adapter because the system is going to a sleeping state.



#### NdisHaltDeviceSurpriseRemoved

The miniport adapter has been surprise removed and the hardware is not present.



#### NdisHaltDeviceFailed

The miniport adapter is being removed because of a hardware failure. Either the miniport driver
       called the 
       <a href="..\ndis\nf-ndis-ndismremoveminiport.md">NdisMRemoveMiniport</a> function or a
       bus driver did not power up the NIC on resume.



#### NdisHaltDeviceInitializationFailed

NDIS could not initialize the miniport adapter for an unknown reason after the 
       <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function completed successfully.



#### NdisHaltDeviceStopped

NDIS is halting the miniport adapter in response to a PnP stop device message.


## -returns



None




## -remarks



A driver specifies the 
    <i>MiniportHaltEx</i> entry point when it calls the 
    <a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">
    NdisMRegisterMiniportDriver</a> function.

NDIS can call 
    <i>MiniportHaltEx</i> at any time after a driver's 
    <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function
    returns successfully. If the driver controls a physical NIC, 
    <i>MiniportHaltEx</i> should stop the NIC. If an NDIS intermediate driver calls the 
    <a href="..\ndis\nf-ndis-ndisimdeinitializedeviceinstance.md">
    NdisIMDeInitializeDeviceInstance</a> function, NDIS calls the 
    <i>MiniportHaltEx</i> function for the driver's virtual device.

<i>MiniportHaltEx</i> must free all resources that were allocated in 
    <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> for a device. 
    <i>MiniportHaltEx</i> also frees any other resources that the driver allocated in
    subsequent operations for that device. The driver must call the reciprocals of the 
    <b>Ndis<i>Xxx</i></b> functions with which it originally allocated the resources. As a general
    rule, a 
    <i>MiniportHaltEx</i> function should call the reciprocal 
    <b>Ndis<i>Xxx</i></b> functions in reverse order to the calls the driver made from 
    <i>MiniportInitializeEx</i>.

If a NIC generates interrupts, a miniport driver's 
    <i>MiniportHaltEx</i> function can be preempted by the driver's 
    <a href="..\ndis\nc-ndis-miniport_isr.md">MiniportInterrupt</a> function until the 
    <i>MiniportHaltEx</i> call to the 
    <a href="..\ndis\nf-ndis-ndismderegisterinterruptex.md">
    NdisMDeregisterInterruptEx</a> function returns. Such a driver's 
    <i>MiniportHaltEx</i> function should disable interrupts, and call 
    <b>
    NdisMDeregisterInterruptEx</b> as soon as possible. Note that a driver can keep getting interrupts
    until 
    <b>
    NdisMDeregisterInterruptEx</b> returns. 
    <b>
    NdisMDeregisterInterruptEx</b> does not return until the driver finishes all the scheduled DPCs (see
    the 
    <a href="..\ndis\nc-ndis-miniport_interrupt_dpc.md">MiniportInterruptDPC</a> function for
    more information).

If the driver has a 
    <a href="..\ndis\nc-ndis-ndis_timer_function.md">NetTimerCallback</a> function that is
    associated with a timer object that could be in the system timer queue, 
    <i>MiniportHaltEx</i> should call the 
    <a href="..\ndis\nf-ndis-ndiscanceltimerobject.md">NdisCancelTimerObject</a> function. If 
    <b>NdisCancelTimerObject</b> fails, the timer could have already fired. In this case, the driver should
    wait for the timer function to complete before the driver returns from 
    <i>MiniportHaltEx</i>.

NDIS does not call 
    <i>MiniportHaltEx</i> if there are outstanding OID requests or send requests. NDIS
    submits no further requests for the affected device after NDIS calls 
    <i>MiniportHaltEx</i>.

If the driver must wait for any operation to complete, 
    <i>MiniportHaltEx</i> can use the 
    <a href="..\ndis\nf-ndis-ndiswaitevent.md">NdisWaitEvent</a> function or the 
    <a href="..\ndis\nf-ndis-ndismsleep.md">NdisMSleep</a> function.

NDIS calls
    <i>MiniportHaltEx</i> at IRQL = PASSIVE_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>MiniportHaltEx</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>MiniportHaltEx</i> function that is named "MyHaltEx", use the <b>MINIPORT_HALT</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>MINIPORT_HALT MyHaltEx;</pre>
</td>
</tr>
</table></span></div>
Then, implement your function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID
 MyHaltEx(
    NDIS_HANDLE  MiniportAdapterContext,
    NDIS_HALT_ACTION  HaltAction
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>MINIPORT_HALT</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_HALT</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also

<a href="..\ndis\nc-ndis-ndis_timer_function.md">NetTimerCallback</a>



<a href="..\ndis\nf-ndis-ndisimdeinitializedeviceinstance.md">
   NdisIMDeInitializeDeviceInstance</a>



<a href="https://msdn.microsoft.com/fd57a2b1-593d-412b-96b5-eabd3ea392e0">Halting a Miniport Adapter</a>



<a href="..\ndis\nc-ndis-miniport_interrupt_dpc.md">MiniportInterruptDPC</a>



<a href="https://msdn.microsoft.com/b47e2cbe-9da3-4600-9afe-b082e60b87fb">Miniport Adapter States and Operations</a>



<a href="..\ndis\nf-ndis-ndismderegisterinterruptex.md">NdisMDeregisterInterruptEx</a>



<a href="https://msdn.microsoft.com/20047ee2-ba37-47c2-858f-36e31ae19154">Miniport Driver Reset and Halt Functions</a>



<a href="..\ndis\nf-ndis-ndismremoveminiport.md">NdisMRemoveMiniport</a>



<a href="..\ndis\nf-ndis-ndiswaitevent.md">NdisWaitEvent</a>



<a href="..\ndis\nc-ndis-miniport_return_net_buffer_lists.md">
   MiniportReturnNetBufferLists</a>



<a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">NdisMRegisterMiniportDriver</a>



<a href="..\ndis\nc-ndis-miniport_isr.md">MiniportInterrupt</a>



<a href="..\ndis\nf-ndis-ndiscanceltimerobject.md">NdisCancelTimerObject</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="..\ndis\nf-ndis-ndismsleep.md">NdisMSleep</a>



<a href="https://msdn.microsoft.com/3ca03511-a912-4ee3-bd9f-1bd8e6996c48">Adapter States of a Miniport Driver</a>



 

 


