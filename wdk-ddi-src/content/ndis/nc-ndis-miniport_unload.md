---
UID: NC:ndis.MINIPORT_UNLOAD
title: MINIPORT_UNLOAD
description: NDIS calls a miniport driver's MiniportDriverUnload function to request the driver to release resources before the system completes a driver unload operation.
old-location: netvista\miniportdriverunload.htm
tech.root: netvista
ms.assetid: 25c803cf-f8a6-4e41-a731-c3ae7f1db211
ms.date: 05/02/2018
ms.keywords: MINIPORT_UNLOAD, MINIPORT_UNLOAD callback, MiniportDriverUnload, MiniportDriverUnload callback function [Network Drivers Starting with Windows Vista], miniport_functions_ref_8f9795d0-00aa-4059-8dbf-8f7eed303cae.xml, ndis/MiniportDriverUnload, netvista.miniportdriverunload
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ndis.h
api_name:
-	MiniportDriverUnload
product:
- Windows
targetos: Windows
req.typenames: 
---

# MINIPORT_UNLOAD callback function


## -description


NDIS calls a miniport driver's 
   <i>MiniportDriverUnload</i> function to request the driver to release resources before the system completes
   a driver unload operation.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_UNLOAD</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param DriverObject [in]

A pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff544174">DRIVER_OBJECT</a> structure that is the driver's
     driver object.


## -returns



None




## -remarks



A driver specifies the 
    <i>MiniportDriverUnload</i> entry point when it calls the 
    <a href="https://msdn.microsoft.com/bed68aa8-499d-41fd-997b-a46316913cc8">
    NdisMRegisterMiniportDriver</a> function.

The driver object that is associated with an NDIS miniport driver specifies an 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564886">Unload</a> routine. The operating system calls the 
    <b>Unload</b> routine when all the devices the miniport driver services have been removed. NDIS provides
    the 
    <b>Unload</b> routine for NDIS drivers. NDIS calls a miniport driver's 
    <i>MiniportDriverUnload</i> function from the 
    <b>Unload</b> routine.

The functionality of the 
    <b>Unload</b> routine is driver-specific. As a general rule, 
    <i>MiniportDriverUnload</i> should undo the operations that were performed in the driver's 
    <b>DriverEntry</b> routine.

A miniport driver calls the 
    <a href="https://msdn.microsoft.com/c428e30d-ce86-4ca0-bc65-45d84a7c910e">
    NdisMDeregisterMiniportDriver</a> function from 
    <i>MiniportDriverUnload</i>.

In addition to 
    <b>NdisMDeregisterMiniportDriver</b>, an intermediate driver also calls the 
    <a href="https://msdn.microsoft.com/792f8f89-ff2c-45d1-bb15-9fcdafd14231">
    NdisDeregisterProtocolDriver</a> function to deregister the protocol interface of the driver. 
    <i>MiniportDriverUnload</i> should also perform any necessary cleanup operations, such as deallocating any
    protocol driver interface resources.

If a miniport driver manages more than one device instance, such as a load-balancing driver, NDIS will
    not call 
    <i>MiniportDriverUnload</i> until after NDIS calls the 
    <a href="https://msdn.microsoft.com/b8d452b4-bef3-4991-87cf-fac15bedfde4">MiniportHaltEx</a> function one time for
    each device instance.

NDIS calls 
    <i>MiniportDriverUnload</i> at IRQL = PASSIVE_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>MiniportDriverUnload</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>MiniportDriverUnload</i> function that is named "MyDriverUnload", use the <b>MINIPORT_UNLOAD</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>MINIPORT_UNLOAD MyDriverUnload;</pre>
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
 MyDriverUnload(
    PDRIVER_OBJECT  DriverObject
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>MINIPORT_UNLOAD</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_UNLOAD</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544174">DRIVER_OBJECT</a>



<a href="https://msdn.microsoft.com/b8d452b4-bef3-4991-87cf-fac15bedfde4">MiniportHaltEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561743">NdisDeregisterProtocolDriver</a>



<a href="https://msdn.microsoft.com/c428e30d-ce86-4ca0-bc65-45d84a7c910e">
   NdisMDeregisterMiniportDriver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563654">NdisMRegisterMiniportDriver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564886">Unload</a>
 

 

