---
UID: NC:ndis.MINIPORT_SHUTDOWN
title: MINIPORT_SHUTDOWN
author: windows-driver-content
description: NDIS calls a miniport driver's MiniportShutdownEx function when the system is shutting down.
old-location: netvista\miniportshutdownex.htm
old-project: netvista
ms.assetid: 7c88ff02-e791-4642-ad40-78f2ef2cba7d
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.miniportshutdownex, MiniportShutdownEx callback function [Network Drivers Starting with Windows Vista], MiniportShutdownEx, MINIPORT_SHUTDOWN, MINIPORT_SHUTDOWN, ndis/MiniportShutdownEx, miniport_functions_ref_1ef84db9-b4af-4e59-9bb8-6f467a0866d5.xml
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	Ndis.h
apiname: 
-	MiniportShutdownEx
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# MINIPORT_SHUTDOWN callback


## -description


NDIS calls a miniport driver's 
   <i>MiniportShutdownEx</i> function when the system is shutting down. This function puts the miniport into the Shutdown state, where no other callback can occur (including <a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a>). For more information about miniport driver states, see <a href="https://msdn.microsoft.com/b47e2cbe-9da3-4600-9afe-b082e60b87fb">Miniport Adapter States and Operations</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_SHUTDOWN</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -prototype


````
MINIPORT_SHUTDOWN MiniportShutdownEx;

VOID MiniportShutdownEx(
  _In_ NDIS_HANDLE          MiniportAdapterContext,
  _In_ NDIS_SHUTDOWN_ACTION ShutdownAction
)
{ ... }
````


## -parameters




### -param MiniportAdapterContext [in]

A handle to a context area that the miniport driver allocated in its 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function.
     The driver uses this context area to maintain state information for a miniport adapter.


### -param ShutdownAction [in]

The reason why NDIS called the shutdown function. The following values are valid:
     




##### - ShutdownAction.NdisShutdownPowerOff

Indicates that NDIS called 
       <i>MiniportShutdownEx</i> because the system is shutting down.


##### - ShutdownAction.NdisShutdownBugCheck

Indicates that NDIS called 
       <i>MiniportShutdownEx</i> because of a system error.


## -returns


None



## -remarks


A driver specifies the 
    <i>MiniportShutdownEx</i> entry point when it calls the 
    <mshelp:link keywords="netvista.ndismregisterminiportdriver" tabindex="0"><b>
    NdisMRegisterMiniportDriver</b></mshelp:link> function.

<i>MiniportShutdownEx</i> restores the miniport adapter to a known initial state (the
    state before NDIS called the miniport driver's 
    <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function for
    the miniport adapter). This makes sure that the miniport adapter is in a known state and ready to be
    reinitialized when the computer is restarted after a system shutdown occurs for any reason, including an
    unrecoverable system error.

<i>MiniportShutdownEx</i> can read or write to I/O ports, memory-mapped device I/O
    space, or bus-specific configuration space by calling the 
    <a href="..\ndis\nf-ndis-ndismgetbusdata.md">NdisMGetBusData</a> or 
    <a href="..\ndis\nf-ndis-ndismsetbusdata.md">NdisMSetBusData</a> function to disable a DMA
    engine, disable interrupts, or reset the hardware to a known state so the hardware can be restarted
    safely.

If NDIS calls 
    <i>MiniportShutdownEx</i> because of an unrecoverable error, the 
    <i>ShutdownAction</i> parameter is set to 
    <b>NdisShutdownBugCheck</b> and 
    <i>MiniportShutdownEx</i> is running at a high IRQL. In this case, the miniport driver
    must not call any 
    <b>Ndis<i>Xxx</i></b> functions except those functions that can be called at any IRQL.

If NDIS calls 
    <i>MiniportShutdownEx</i> because of a user-initiated shutdown, 
    <i>MiniportShutdownEx</i> runs at IRQL = PASSIVE_LEVEL and the miniport driver can
    call other 
    <b>Ndis<i>Xxx</i></b> functions.

If NDIS calls <i>MiniportShutdownEx</i> because of an unrecoverable error, the <i>ShutdownAction</i> parameter is set to <b>NdisShutdownBugCheck</b> and <i>MiniportShutdownEx</i> is running at a high IRQL. In this case, the miniport driver must not call any <b>Ndis<i>Xxx</i></b> functions except those functions that can be called at any IRQL.  Starting with NDIS 6.30 miniports, NDIS does not call <i>MiniportShutdownEx</i> during a BugCheck unless the miniport provides the <b>NDIS_MINIPORT_ATTRIBUTES_REGISTER_BUGCHECK_CALLBACK</b> flag in its adapter registration attributes.

If the value of <i>ShutdownAction</i> is <b>NdisShutdownPowerOff</b>, the miniport driver may optionally free its resources. However, this is neither required nor encouraged, because the system shutdown makes it unnecessary.

If the value of <i>ShutdownAction</i> is <b>NdisShutdownBugCheck</b>, the miniport driver must not free its resources.<div class="alert"><b>Important</b>  If <a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a> causes a system error, then the miniport driver will see a nested call to <i>MiniportShutdownEx</i> with <i>ShutdownAction</i><b>NdisShutdownBugCheck</b>. In this case, <i>MiniportShutdownEx</i> should return immediately without doing any work.</div>
<div> </div>

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>To define a <i>MiniportShutdownEx</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>MiniportShutdownEx</i> function that is named "MyShutdownEx", use the <b>MINIPORT_SHUTDOWN</b> type as shown in this code example:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>MINIPORT_SHUTDOWN MyShutdownEx;</pre>
</td>
</tr>
</table></span></div>Then, implement your function as follows:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID
 MyShutdownEx(
    NDIS_HANDLE  MiniportAdapterContext,
    NDIS_SHUTDOWN_ACTION  ShutdownAction
    )
  {...}</pre>
</td>
</tr>
</table></span></div>The <b>MINIPORT_SHUTDOWN</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_SHUTDOWN</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 



## -see-also

<a href="..\ndis\nf-ndis-ndismgetbusdata.md">NdisMGetBusData</a>

<a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">NdisMRegisterMiniportDriver</a>

<a href="..\ndis\nf-ndis-ndismsetbusdata.md">NdisMSetBusData</a>

<a href="https://msdn.microsoft.com/57d964f1-03c7-4b54-9d04-1d187c96e052">Miniport Adapter Shutdown</a>

<a href="https://msdn.microsoft.com/3ca03511-a912-4ee3-bd9f-1bd8e6996c48">Adapter States of a Miniport Driver</a>

<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>

<a href="https://msdn.microsoft.com/b47e2cbe-9da3-4600-9afe-b082e60b87fb">Miniport Adapter States and Operations</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_SHUTDOWN callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

