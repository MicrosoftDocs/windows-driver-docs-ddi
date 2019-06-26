---
UID: NS:ndis._NDIS_MINIPORT_INTERRUPT_CHARACTERISTICS
title: _NDIS_MINIPORT_INTERRUPT_CHARACTERISTICS (ndis.h)
description: An NDIS miniport driver defines its interrupt characteristics in an NDIS_MINIPORT_INTERRUPT_CHARACTERISTICS structure and passes the structure to the NdisMRegisterInterruptEx function.
old-location: netvista\ndis_miniport_interrupt_characteristics.htm
tech.root: netvista
ms.assetid: f4176e2d-d8d2-4e75-bccb-0c452da4d703
ms.date: 05/02/2018
ms.keywords: "*PNDIS_MINIPORT_INTERRUPT_CHARACTERISTICS, NDIS_MINIPORT_INTERRUPT_CHARACTERISTICS, NDIS_MINIPORT_INTERRUPT_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], PNDIS_MINIPORT_INTERRUPT_CHARACTERISTICS, PNDIS_MINIPORT_INTERRUPT_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_MINIPORT_INTERRUPT_CHARACTERISTICS, ndis/NDIS_MINIPORT_INTERRUPT_CHARACTERISTICS, ndis/PNDIS_MINIPORT_INTERRUPT_CHARACTERISTICS, ndis_interrupts_structures_ref_87c0c090-a28d-4195-b73d-52e3a188a80b.xml, netvista.ndis_miniport_interrupt_characteristics"
ms.topic: struct
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ndis.h
api_name:
- NDIS_MINIPORT_INTERRUPT_CHARACTERISTICS
product:
- Windows
targetos: Windows
req.typenames: NDIS_MINIPORT_INTERRUPT_CHARACTERISTICS, *PNDIS_MINIPORT_INTERRUPT_CHARACTERISTICS
---

# _NDIS_MINIPORT_INTERRUPT_CHARACTERISTICS structure


## -description


An NDIS miniport driver defines its interrupt characteristics in an
  NDIS_MINIPORT_INTERRUPT_CHARACTERISTICS structure and passes the structure to the 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismregisterinterruptex">
  NdisMRegisterInterruptEx</a> function.


## -struct-fields




### -field Header

The 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_MINIPORT_INTERRUPT_CHARACTERISTICS structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_MINIPORT_INTERRUPT, the 
     <b>Revision</b> member to NDIS_MINIPORT_INTERRUPT_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_MINIPORT_INTERRUPT_CHARACTERISTICS_REVISION_1.


### -field InterruptHandler

The entry point for the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_isr">MiniportInterrupt</a> function that is
     associated with this interrupt.


### -field InterruptDpcHandler

The entry point for the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_interrupt_dpc">MiniportInterruptDPC</a> function
     that is associated with this interrupt.


### -field DisableInterruptHandler

The entry point for the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_disable_interrupt">
     MiniportDisableInterruptEx</a> function.


### -field EnableInterruptHandler

The entry point for the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_enable_interrupt">
     MiniportEnableInterruptEx</a> function.


### -field MsiSupported

Set this member to <b>TRUE</b> if the miniport driver supports message-signaled interrupt (MSI) service
     functions. The miniport driver must provide entry points for the MSI service functions.
     

Setting this value to <b>FALSE</b> indicates that MSI is not supported. The MSI service function entry
     points should be set to <b>NULL</b>.


### -field MsiSyncWithAllMessages

Set this member to <b>TRUE</b> if the miniport driver must serialize all MSI service functions. 
     

Setting this value to <b>TRUE</b> can degrade interrupt performance. It is more efficient for multiple
     interrupt service functions that handle different messages to run concurrently.


### -field MessageInterruptHandler

The entry point for the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_message_interrupt">
     MiniportMessageInterrupt</a> function, if it exists, that is associated with this interrupt. If the
     driver does not support message interrupts, set this member to <b>NULL</b>.


### -field MessageInterruptDpcHandler

The entry point for the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_message_interrupt_dpc">
     MiniportMessageInterruptDPC</a> function, if any, that is associated with this interrupt. If the
     driver does not support message-signaled interrupts, set this member to <b>NULL</b>.


### -field DisableMessageInterruptHandler

The entry point for the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_disable_message_interrupt">
     MiniportDisableMessageInterrupt</a> function, if any. If the driver does not support message signaled
     interrupts, set this member to <b>NULL</b>.


### -field EnableMessageInterruptHandler

The entry point for the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_enable_message_interrupt">
     MiniportEnableMessageInterrupt</a> function, if any. If the driver does not support message-signaled
     interrupts, set this member to <b>NULL</b>.


### -field InterruptType

A variable of type <b>NDIS_INTERRUPT_TYPE</b>. NDIS sets this variable to indicate which kind of
     interrupt it granted to the miniport driver. If the driver supports MSI, it must check this value if 
     <b>NdisMRegisterInterruptEx</b> returns NDIS_STATUS_SUCCESS. If 
     <b>InterruptType</b> is set to <b>NDIS_CONNECT_LINE_BASED</b>, then NDIS granted the driver a line-based
     interrupt, which can happen even if the driver supports message-signaled interrupts. If 
     <b>InterruptType</b> is set to <b>NDIS_CONNECT_MESSAGE_BASED</b>, then NDIS granted the driver a
     message-signaled interrupt. In this case, the driver can access 
     <b>MessageInfoTable</b> to obtain the interrupt information.


### -field MessageInfoTable

An NDIS-supplied pointer to an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_io_interrupt_message_info">
     IO_INTERRUPT_MESSAGE_INFO</a> structure. 

<ul>
<li>
If 
     <b>InterruptType</b> is <b>NDIS_CONNECT_MESSAGE_BASED</b>, NDIS initializes an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_io_interrupt_message_info">IO_INTERRUPT_MESSAGE_INFO</a>
     structure with information about the interrupt and sets 
     <b>MessageInfoTable</b> to a pointer to the structure. Miniport drivers must not modify the
     structure.

</li>
<li>
If <b>InterruptType</b> is <b>NDIS_CONNECT_LINE_BASED</b>, <b>MessageInfoTable</b> must be NULL.

</li>
</ul>

## -remarks



A miniport driver calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismregisterinterruptex">NdisMRegisterInterruptEx</a> function
    to register an interrupt. The driver allocates and initializes an <b>NDIS_MINIPORT_INTERRUPT_CHARACTERISTICS</b>
    structure to specify the interrupt characteristics and handler entry points and passes the structure to 
    <b>NdisMRegisterInterruptEx</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_io_interrupt_message_info">IO_INTERRUPT_MESSAGE_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_disable_interrupt">MiniportDisableInterruptEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_disable_message_interrupt">
   MiniportDisableMessageInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_enable_interrupt">MiniportEnableInterruptEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_enable_message_interrupt">
   MiniportEnableMessageInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_isr">MiniportInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_interrupt_dpc">MiniportInterruptDPC</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_message_interrupt">MiniportMessageInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_message_interrupt_dpc">MiniportMessageInterruptDPC</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndismregisterinterruptex">NdisMRegisterInterruptEx</a>
 

 

