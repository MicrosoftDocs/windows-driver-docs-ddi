---
UID: NC:ndis.MINIPORT_UNLOAD
title: MINIPORT_UNLOAD (ndis.h)
description: NDIS calls a miniport driver's MiniportDriverUnload function to request the driver to release resources before the system completes a driver unload operation.
old-location: netvista\miniportdriverunload.htm
tech.root: netvista
ms.assetid: 25c803cf-f8a6-4e41-a731-c3ae7f1db211
ms.date: 05/02/2018
keywords: ["MINIPORT_UNLOAD callback function"]
ms.keywords: MINIPORT_UNLOAD, MINIPORT_UNLOAD callback, MiniportDriverUnload, MiniportDriverUnload callback function [Network Drivers Starting with Windows Vista], miniport_functions_ref_8f9795d0-00aa-4059-8dbf-8f7eed303cae.xml, ndis/MiniportDriverUnload, netvista.miniportdriverunload
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
 - MINIPORT_UNLOAD
 - ndis/MINIPORT_UNLOAD
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ndis.h
api_name:
 - MiniportDriverUnload
---

# MINIPORT_UNLOAD callback function


## -description

NDIS calls a miniport driver's 
   <i>MiniportDriverUnload</i> function to request the driver to release resources before the system completes
   a driver unload operation.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_UNLOAD</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters

### -param DriverObject 

[in]
A pointer to a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_driver_object">DRIVER_OBJECT</a> structure that is the driver's
     driver object.

## -remarks

A driver specifies the 
    <i>MiniportDriverUnload</i> entry point when it calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterminiportdriver">
    NdisMRegisterMiniportDriver</a> function.

The driver object that is associated with an NDIS miniport driver specifies an 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_unload">Unload</a> routine. The operating system calls the 
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
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismderegisterminiportdriver">
    NdisMDeregisterMiniportDriver</a> function from 
    <i>MiniportDriverUnload</i>.

In addition to 
    <b>NdisMDeregisterMiniportDriver</b>, an intermediate driver also calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisderegisterprotocoldriver">
    NdisDeregisterProtocolDriver</a> function to deregister the protocol interface of the driver. 
    <i>MiniportDriverUnload</i> should also perform any necessary cleanup operations, such as deallocating any
    protocol driver interface resources.

If a miniport driver manages more than one device instance, such as a load-balancing driver, NDIS will
    not call 
    <i>MiniportDriverUnload</i> until after NDIS calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a> function one time for
    each device instance.

NDIS calls 
    <i>MiniportDriverUnload</i> at IRQL = PASSIVE_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>MiniportDriverUnload</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>MiniportDriverUnload</i> function that is named "MyDriverUnload", use the <b>MINIPORT_UNLOAD</b> type as shown in this code example:


```
MINIPORT_UNLOAD MyDriverUnload;
```

Then, implement your function as follows:


```
_Use_decl_annotations_
VOID
 MyDriverUnload(
    PDRIVER_OBJECT  DriverObject
    )
  {...}
```

The <b>MINIPORT_UNLOAD</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_UNLOAD</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_driver_object">DRIVER_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisderegisterprotocoldriver">NdisDeregisterProtocolDriver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismderegisterminiportdriver">
   NdisMDeregisterMiniportDriver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterminiportdriver">NdisMRegisterMiniportDriver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_unload">Unload</a>

