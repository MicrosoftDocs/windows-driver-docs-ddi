---
UID: NS:ndis._NDIS_MINIPORT_INTERRUPT_CHARACTERISTICS
title: "_NDIS_MINIPORT_INTERRUPT_CHARACTERISTICS"
author: windows-driver-content
description: An NDIS miniport driver defines its interrupt characteristics in an NDIS_MINIPORT_INTERRUPT_CHARACTERISTICS structure and passes the structure to the NdisMRegisterInterruptEx function.
old-location: netvista\ndis_miniport_interrupt_characteristics.htm
old-project: netvista
ms.assetid: f4176e2d-d8d2-4e75-bccb-0c452da4d703
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "*PNDIS_MINIPORT_INTERRUPT_CHARACTERISTICS, ndis/PNDIS_MINIPORT_INTERRUPT_CHARACTERISTICS, NDIS_MINIPORT_INTERRUPT_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], PNDIS_MINIPORT_INTERRUPT_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], PNDIS_MINIPORT_INTERRUPT_CHARACTERISTICS, NDIS_MINIPORT_INTERRUPT_CHARACTERISTICS, ndis_interrupts_structures_ref_87c0c090-a28d-4195-b73d-52e3a188a80b.xml, netvista.ndis_miniport_interrupt_characteristics, ndis/NDIS_MINIPORT_INTERRUPT_CHARACTERISTICS, _NDIS_MINIPORT_INTERRUPT_CHARACTERISTICS"
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: See Remarks section
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ndis.h
apiname:
-	NDIS_MINIPORT_INTERRUPT_CHARACTERISTICS
product: Windows
targetos: Windows
req.typenames: "*PNDIS_MINIPORT_INTERRUPT_CHARACTERISTICS, NDIS_MINIPORT_INTERRUPT_CHARACTERISTICS"
---

# _NDIS_MINIPORT_INTERRUPT_CHARACTERISTICS structure


## -description


An NDIS miniport driver defines its interrupt characteristics in an
  NDIS_MINIPORT_INTERRUPT_CHARACTERISTICS structure and passes the structure to the 
  <a href="..\ndis\nf-ndis-ndismregisterinterruptex.md">
  NdisMRegisterInterruptEx</a> function.


## -syntax


````
typedef struct _NDIS_MINIPORT_INTERRUPT_CHARACTERISTICS {
  NDIS_OBJECT_HEADER                     Header;
  MINIPORT_ISR_HANDLER                   InterruptHandler;
  MINIPORT_INTERRUPT_DPC_HANDLER         InterruptDpcHandler;
  MINIPORT_DISABLE_INTERRUPT_HANDLER     DisableInterruptHandler;
  MINIPORT_ENABLE_INTERRUPT_HANDLER      EnableInterruptHandler;
  BOOLEAN                                MsiSupported;
  BOOLEAN                                MsiSyncWithAllMessages;
  MINIPORT_MSI_ISR_HANDLER               MessageInterruptHandler;
  MINIPORT_MSI_INTERRUPT_DPC_HANDLER     MessageInterruptDpcHandler;
  MINIPORT_DISABLE_MSI_INTERRUPT_HANDLER DisableMessageInterruptHandler;
  MINIPORT_ENABLE_MSI_INTERRUPT_HANDLER  EnableMessageInterruptHandler;
  NDIS_INTERRUPT_TYPE                    InterruptType;
  PIO_INTERRUPT_MESSAGE_INFO             MessageInfoTable;
} NDIS_MINIPORT_INTERRUPT_CHARACTERISTICS, *PNDIS_MINIPORT_INTERRUPT_CHARACTERISTICS;
````


## -struct-fields




### -field Header

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_MINIPORT_INTERRUPT_CHARACTERISTICS structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_MINIPORT_INTERRUPT, the 
     <b>Revision</b> member to NDIS_MINIPORT_INTERRUPT_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_MINIPORT_INTERRUPT_CHARACTERISTICS_REVISION_1.


### -field InterruptHandler

The entry point for the 
     <a href="..\ndis\nc-ndis-miniport_isr.md">MiniportInterrupt</a> function that is
     associated with this interrupt.


### -field InterruptDpcHandler

The entry point for the 
     <a href="..\ndis\nc-ndis-miniport_interrupt_dpc.md">MiniportInterruptDPC</a> function
     that is associated with this interrupt.


### -field DisableInterruptHandler

The entry point for the 
     <a href="..\ndis\nc-ndis-miniport_disable_interrupt.md">
     MiniportDisableInterruptEx</a> function.


### -field EnableInterruptHandler

The entry point for the 
     <a href="..\ndis\nc-ndis-miniport_enable_interrupt.md">
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
     <a href="..\ndis\nc-ndis-miniport_message_interrupt.md">
     MiniportMessageInterrupt</a> function, if it exists, that is associated with this interrupt. If the
     driver does not support message interrupts, set this member to <b>NULL</b>.


### -field MessageInterruptDpcHandler

The entry point for the 
     <a href="..\ndis\nc-ndis-miniport_message_interrupt_dpc.md">
     MiniportMessageInterruptDPC</a> function, if any, that is associated with this interrupt. If the
     driver does not support message-signaled interrupts, set this member to <b>NULL</b>.


### -field DisableMessageInterruptHandler

The entry point for the 
     <a href="..\ndis\nc-ndis-miniport_disable_message_interrupt.md">
     MiniportDisableMessageInterrupt</a> function, if any. If the driver does not support message signaled
     interrupts, set this member to <b>NULL</b>.


### -field EnableMessageInterruptHandler

The entry point for the 
     <a href="..\ndis\nc-ndis-miniport_enable_message_interrupt.md">
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
     <a href="..\wdm\ns-wdm-_io_interrupt_message_info.md">
     IO_INTERRUPT_MESSAGE_INFO</a> structure. 

<ul>
<li>
If 
     <b>InterruptType</b> is <b>NDIS_CONNECT_MESSAGE_BASED</b>, NDIS initializes an <a href="..\wdm\ns-wdm-_io_interrupt_message_info.md">IO_INTERRUPT_MESSAGE_INFO</a>
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
    <a href="..\ndis\nf-ndis-ndismregisterinterruptex.md">NdisMRegisterInterruptEx</a> function
    to register an interrupt. The driver allocates and initializes an <b>NDIS_MINIPORT_INTERRUPT_CHARACTERISTICS</b>
    structure to specify the interrupt characteristics and handler entry points and passes the structure to 
    <b>NdisMRegisterInterruptEx</b>.




## -see-also

<a href="..\ndis\nc-ndis-miniport_message_interrupt_dpc.md">MiniportMessageInterruptDPC</a>



<a href="..\wdm\ns-wdm-_io_interrupt_message_info.md">IO_INTERRUPT_MESSAGE_INFO</a>



<a href="..\ndis\nc-ndis-miniport_disable_message_interrupt.md">
   MiniportDisableMessageInterrupt</a>



<a href="..\ndis\nc-ndis-miniport_enable_message_interrupt.md">
   MiniportEnableMessageInterrupt</a>



<a href="..\ndis\nf-ndis-ndismregisterinterruptex.md">NdisMRegisterInterruptEx</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="..\ndis\nc-ndis-miniport_interrupt_dpc.md">MiniportInterruptDPC</a>



<a href="..\ndis\nc-ndis-miniport_disable_interrupt.md">MiniportDisableInterruptEx</a>



<a href="..\ndis\nc-ndis-miniport_message_interrupt.md">MiniportMessageInterrupt</a>



<a href="..\ndis\nc-ndis-miniport_enable_interrupt.md">MiniportEnableInterruptEx</a>



<a href="..\ndis\nc-ndis-miniport_isr.md">MiniportInterrupt</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_MINIPORT_INTERRUPT_CHARACTERISTICS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

