---
UID: NC:ndis.MINIPORT_UNLOAD
title: MINIPORT_UNLOAD
author: windows-driver-content
description: NDIS calls a miniport driver's MiniportDriverUnload function to request the driver to release resources before the system completes a driver unload operation.
old-location: netvista\miniportdriverunload.htm
old-project: netvista
ms.assetid: 25c803cf-f8a6-4e41-a731-c3ae7f1db211
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.miniportdriverunload, MiniportDriverUnload callback function [Network Drivers Starting with Windows Vista], MiniportDriverUnload, MINIPORT_UNLOAD, MINIPORT_UNLOAD, ndis/MiniportDriverUnload, miniport_functions_ref_8f9795d0-00aa-4059-8dbf-8f7eed303cae.xml
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Ndis.h
apiname:
-	MiniportDriverUnload
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# MINIPORT_UNLOAD callback


## -description


NDIS calls a miniport driver's 
   <i>MiniportDriverUnload</i> function to request the driver to release resources before the system completes
   a driver unload operation.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_UNLOAD</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -prototype


````
MINIPORT_UNLOAD MiniportDriverUnload;

VOID MiniportDriverUnload(
  _In_ PDRIVER_OBJECT DriverObject
)
{ ... }
````


## -parameters




### -param DriverObject [in]

A pointer to a 
     <a href="..\wdm\ns-wdm-_driver_object.md">DRIVER_OBJECT</a> structure that is the driver's
     driver object.


## -returns


None



## -remarks


A driver specifies the 
    <i>MiniportDriverUnload</i> entry point when it calls the 
    <a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">
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
    <a href="..\ndis\nf-ndis-ndismderegisterminiportdriver.md">
    NdisMDeregisterMiniportDriver</a> function from 
    <i>MiniportDriverUnload</i>.

In addition to 
    <b>NdisMDeregisterMiniportDriver</b>, an intermediate driver also calls the 
    <a href="..\ndis\nf-ndis-ndisderegisterprotocoldriver.md">
    NdisDeregisterProtocolDriver</a> function to deregister the protocol interface of the driver. 
    <i>MiniportDriverUnload</i> should also perform any necessary cleanup operations, such as deallocating any
    protocol driver interface resources.

If a miniport driver manages more than one device instance, such as a load-balancing driver, NDIS will
    not call 
    <i>MiniportDriverUnload</i> until after NDIS calls the 
    <a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a> function one time for
    each device instance.

NDIS calls 
    <i>MiniportDriverUnload</i> at IRQL = PASSIVE_LEVEL.
<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>To define a <i>MiniportDriverUnload</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

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
</table></span></div>Then, implement your function as follows:
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
</table></span></div>The <b>MINIPORT_UNLOAD</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_UNLOAD</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 



## -see-also

<a href="..\wdm\ns-wdm-_driver_object.md">DRIVER_OBJECT</a>

<a href="..\ndis\nf-ndis-ndisderegisterprotocoldriver.md">NdisDeregisterProtocolDriver</a>

<a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">NdisMRegisterMiniportDriver</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564886">Unload</a>

<a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a>

<a href="..\ndis\nf-ndis-ndismderegisterminiportdriver.md">
   NdisMDeregisterMiniportDriver</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_UNLOAD callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

