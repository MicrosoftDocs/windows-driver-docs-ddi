---
UID: NC:ndis.MINIPORT_ENABLE_MESSAGE_INTERRUPT
title: MINIPORT_ENABLE_MESSAGE_INTERRUPT (ndis.h)
description: NDIS can call a miniport driver's MiniportEnableMessageInterrupt function to enable a message interrupt for diagnostic and troubleshooting purposes.
old-location: netvista\miniportenablemessageinterrupt.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["MINIPORT_ENABLE_MESSAGE_INTERRUPT callback function"]
ms.keywords: MINIPORT_ENABLE_MESSAGE_INTERRUPT, MINIPORT_ENABLE_MESSAGE_INTERRUPT callback, MiniportEnableMessageInterrupt, MiniportEnableMessageInterrupt callback function [Network Drivers Starting with Windows Vista], ndis/MiniportEnableMessageInterrupt, ndis_interrupts_miniport_functions_ref_cc88ce4b-e75b-4da8-89aa-3d449451a0d3.xml, netvista.miniportenablemessageinterrupt
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
req.irql: DIRQL (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - MINIPORT_ENABLE_MESSAGE_INTERRUPT
 - ndis/MINIPORT_ENABLE_MESSAGE_INTERRUPT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ndis.h
api_name:
 - MINIPORT_ENABLE_MESSAGE_INTERRUPT
---

# MINIPORT_ENABLE_MESSAGE_INTERRUPT callback function


## -description

NDIS can call a miniport driver's 
   <i>MiniportEnableMessageInterrupt</i> function to enable a message interrupt for diagnostic and
   troubleshooting purposes.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_ENABLE_MESSAGE_INTERRUPT</b> type.
   For more information, see the following Examples section.</div><div> </div>

## -parameters

### -param MiniportInterruptContext [in]


A handle to a block of context information. The miniport driver supplied this handle in the 
     <i>MiniportInterruptContext</i> parameter that the miniport driver passed to the 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterinterruptex">
     NdisMRegisterInterruptEx</a> function.

### -param MessageId [in]


A message-signaled interrupt. 
     <i>MessageId</i> is an index to the 
     <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_interrupt_message_info_entry">
     IO_INTERRUPT_MESSAGE_INFO_ENTRY</a> structures inside a 
     <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_interrupt_message_info">
     IO_INTERRUPT_MESSAGE_INFO</a> structure. NDIS passes a pointer to the associated
     IO_INTERRUPT_MESSAGE_INFO structure at the 
     <b>MessageInfoTable</b> member when the driver successfully registers for MSI with the 
     <b>NdisMRegisterInterruptEx</b> function.

## -remarks

A miniport driver must provide a
    <i>MiniportEnableMessageInterrupt</i> function if the driver calls the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterinterruptex">NdisMRegisterInterruptEx</a> function
    to register an interrupt.

Miniport drivers should disable and enable a message interrupt as explained in the 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_message_interrupt">MiniportMessageInterrupt</a> and 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_message_interrupt_dpc">
    MiniportMessageInterruptDpc</a> reference pages.

NDIS calls the 
    <i>MiniportEnableMessageInterrupt</i> and 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_disable_message_interrupt">
    MiniportDisableMessageInterrupt</a> functions to enable and disable a message interrupt for diagnostic
    and troubleshooting purposes. Typically, 
    <i>MiniportEnableMessageInterrupt</i> and 
    <i>MiniportDisableMessageInterrupt</i> access miniport driver resources that are shared by the 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_message_interrupt">
    MiniportMessageInterrupt</a> function. Therefore, NDIS calls these handlers at DIRQL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>MiniportEnableMessageInterrupt</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>MiniportEnableMessageInterrupt</i> function that is named "MyEnableMessageInterrupt", use the <b>MINIPORT_ENABLE_MESSAGE_INTERRUPT</b> type as shown in this code example:


```
MINIPORT_ENABLE_MESSAGE_INTERRUPT MyEnableMessageInterrupt;
```

Then, implement your function as follows:


```
_Use_decl_annotations_
VOID
 MyEnableMessageInterrupt(
    __in  NDIS_HANDLE  MiniportInterruptContext,
    __in  ULONG  MessageId
    )
  {...}
```

The <b>MINIPORT_ENABLE_MESSAGE_INTERRUPT</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_ENABLE_MESSAGE_INTERRUPT</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="/visualstudio/code-quality/annotating-function-behavior">Annotating Function Behavior</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_interrupt_message_info">IO_INTERRUPT_MESSAGE_INFO</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_interrupt_message_info_entry">
   IO_INTERRUPT_MESSAGE_INFO_ENTRY</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_disable_message_interrupt">
   MiniportDisableMessageInterrupt</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_message_interrupt">MiniportMessageInterrupt</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_message_interrupt_dpc">MiniportMessageInterruptDPC</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_interrupt_characteristics">
   NDIS_MINIPORT_INTERRUPT_CHARACTERISTICS</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterinterruptex">NdisMRegisterInterruptEx</a>

