---
UID: NC:ndis.MINIPORT_DISABLE_MESSAGE_INTERRUPT
title: MINIPORT_DISABLE_MESSAGE_INTERRUPT (ndis.h)
description: NDIS can call a miniport driver's MiniportDisableMessageInterrupt handler to disable a message interrupt for diagnostic and troubleshooting purposes.
old-location: netvista\miniportdisablemessageinterrupt.htm
tech.root: netvista
ms.assetid: 68d2076d-c991-4219-b6c3-2399ff5c11a3
ms.date: 05/02/2018
ms.keywords: MINIPORT_DISABLE_MESSAGE_INTERRUPT, MINIPORT_DISABLE_MESSAGE_INTERRUPT callback, MiniportDisableMessageInterrupt, MiniportDisableMessageInterrupt callback function [Network Drivers Starting with Windows Vista], ndis/MiniportDisableMessageInterrupt, ndis_interrupts_miniport_functions_ref_50d58bcc-7d77-4ca8-9419-74dd1602177d.xml, netvista.miniportdisablemessageinterrupt
ms.topic: callback
f1_keywords:
 - "ndis/MiniportDisableMessageInterrupt"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ndis.h
api_name:
- MiniportDisableMessageInterrupt
product:
- Windows
targetos: Windows
req.typenames: 
---

# MINIPORT_DISABLE_MESSAGE_INTERRUPT callback function


## -description


NDIS can call a miniport driver's 
   <i>MiniportDisableMessageInterrupt</i> handler to disable a message interrupt for diagnostic and
   troubleshooting purposes.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_DISABLE_MESSAGE_INTERRUPT</b> type.
   For more information, see the following Examples section.</div><div> </div>

## -parameters




### -param MiniportInterruptContext [in]

A handle to a block of context information. The miniport driver supplied this handle in the 
     <i>MiniportInterruptContext</i> parameter that the miniport driver passed to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterinterruptex">
     NdisMRegisterInterruptEx</a> function.


### -param MessageId [in]

A message-signaled interrupt. 
     <i>MessageId</i> is an index to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_interrupt_message_info_entry">
     IO_INTERRUPT_MESSAGE_INFO_ENTRY</a> structures inside a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_interrupt_message_info">
     IO_INTERRUPT_MESSAGE_INFO</a> structure. NDIS passes a pointer to the associated
     IO_INTERRUPT_MESSAGE_INFO structure at the 
     <b>MessageInfoTable</b> member when the driver successfully registers for MSI with the 
     <b>NdisMRegisterInterruptEx</b> function.


## -remarks



A miniport driver must provide a
    <i>MiniportDisableMessageInterrupt</i> function if the driver calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterinterruptex">NdisMRegisterInterruptEx</a> function
    to register an interrupt.

Miniport drivers should disable and enable a message interrupt as explained in the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_message_interrupt">MiniportMessageInterrupt</a> and 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_message_interrupt_dpc">
    MiniportMessageInterruptDpc</a> reference pages.

NDIS calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_enable_message_interrupt">
    MiniportEnableMessageInterrupt</a> and 
    <i>MiniportDisableMessageInterrupt</i> functions to enable and disable interrupts for diagnostic and
    troubleshooting purposes. Typically, 
    <i>MiniportEnableMessageInterrupt</i> and 
    <i>MiniportDisableMessageInterrupt</i> access miniport driver resources that are shared by the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_message_interrupt">
    MiniportMessageInterrupt</a> function. Therefore, NDIS calls these handlers at DIRQL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>MiniportDisableMessageInterrupt</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>MiniportDisableMessageInterrupt</i> function that is named "MyDisableMessageInterrupt", use the <b>MINIPORT_DISABLE_MESSAGE_INTERRUPT</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>MINIPORT_DISABLE_MESSAGE_INTERRUPT MyDisableMessageInterrupt;</pre>
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
 MyDisableMessageInterrupt(
    NDIS_HANDLE  MiniportInterruptContext,
    ULONG  MessageId
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>MINIPORT_DISABLE_MESSAGE_INTERRUPT</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_DISABLE_MESSAGE_INTERRUPT</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_interrupt_message_info">IO_INTERRUPT_MESSAGE_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_interrupt_message_info_entry">
   IO_INTERRUPT_MESSAGE_INFO_ENTRY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_enable_message_interrupt">
   MiniportEnableMessageInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_message_interrupt">MiniportMessageInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_message_interrupt_dpc">MiniportMessageInterruptDPC</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_interrupt_characteristics">
   NDIS_MINIPORT_INTERRUPT_CHARACTERISTICS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterinterruptex">NdisMRegisterInterruptEx</a>
 

 

