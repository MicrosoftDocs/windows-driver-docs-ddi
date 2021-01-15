---
UID: NC:ndis.MINIPORT_DISABLE_INTERRUPT
title: MINIPORT_DISABLE_INTERRUPT (ndis.h)
description: NDIS can call a miniport driver's MiniportDisableInterruptEx handler to disable interrupts for diagnostic and troubleshooting purposes.
old-location: netvista\miniportdisableinterruptex.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["MINIPORT_DISABLE_INTERRUPT callback function"]
ms.keywords: MINIPORT_DISABLE_INTERRUPT, MINIPORT_DISABLE_INTERRUPT callback, MiniportDisableInterruptEx, MiniportDisableInterruptEx callback function [Network Drivers Starting with Windows Vista], ndis/MiniportDisableInterruptEx, ndis_interrupts_miniport_functions_ref_985ddb3d-4a38-4c96-8599-17f211d47b49.xml, netvista.miniportdisableinterruptex
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
targetos: Windows
req.typenames: 
f1_keywords:
 - MINIPORT_DISABLE_INTERRUPT
 - ndis/MINIPORT_DISABLE_INTERRUPT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ndis.h
api_name:
 - MINIPORT_DISABLE_INTERRUPT
---

# MINIPORT_DISABLE_INTERRUPT callback function


## -description

NDIS can call a miniport driver's 
   <i>MiniportDisableInterruptEx</i> handler to disable interrupts for diagnostic and troubleshooting
   purposes.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_DISABLE_INTERRUPT</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters

### -param MiniportInterruptContext 

[in]
A handle to a block of context information. The miniport driver supplied this handle in the 
     <i>MiniportInterruptContext</i> parameter that the miniport driver passed to the 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterinterruptex">
     NdisMRegisterInterruptEx</a> function.

## -remarks

A miniport driver must provide a
    <i>MiniportDisableInterruptEx</i> handler if the driver calls the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterinterruptex">NdisMRegisterInterruptEx</a> function
    to register an interrupt.

Miniport drivers should disable and enable interrupts as explained in the 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_isr">MiniportInterrupt</a> and 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_interrupt_dpc">MiniportInterruptDpc</a> reference
    pages.

NDIS calls the 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_enable_interrupt">MiniportEnableInterruptEx</a> and    
    <i>MiniportDisableInterruptEx</i> functions to enable and disable interrupts for diagnostic and
    troubleshooting purposes. Typically, 
    <i>MiniportEnableInterruptEx</i> and 
    <i>MiniportDisableInterruptEx</i> access miniport driver resources that are shared by the 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_isr">MiniportInterrupt</a> function.
    Therefore, NDIS calls these handlers at DIRQL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>MiniportDisableInterruptEx</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>MiniportDisableInterruptEx</i> function that is named "MyDisableInterruptEx", use the <b>MINIPORT_DISABLE_INTERRUPT</b> type as shown in this code example:


```
MINIPORT_DISABLE_INTERRUPT MyDisableInterruptEx;
```

Then, implement your function as follows:


```
_Use_decl_annotations_
VOID
 MyDisableInterruptEx(
    NDIS_HANDLE  MiniportInterruptContext
    )
  {...}
```

The <b>MINIPORT_DISABLE_INTERRUPT</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_DISABLE_INTERRUPT</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="/visualstudio/code-quality/annotating-function-behavior">Annotating Function Behavior</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_enable_interrupt">MiniportEnableInterruptEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_isr">MiniportInterrupt</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_interrupt_dpc">MiniportInterruptDPC</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_interrupt_characteristics">
   NDIS_MINIPORT_INTERRUPT_CHARACTERISTICS</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterinterruptex">NdisMRegisterInterruptEx</a>

