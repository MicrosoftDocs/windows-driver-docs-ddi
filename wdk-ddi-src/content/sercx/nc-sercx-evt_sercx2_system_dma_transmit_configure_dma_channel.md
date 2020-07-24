---
UID: NC:sercx.EVT_SERCX2_SYSTEM_DMA_TRANSMIT_CONFIGURE_DMA_CHANNEL
title: EVT_SERCX2_SYSTEM_DMA_TRANSMIT_CONFIGURE_DMA_CHANNEL (sercx.h)
description: The EvtSerCx2SystemDmaTransmitConfigureDmaChannel event callback function is called by version 2 of the serial framework extension (SerCx2) to let the serial controller driver do any custom configuration of the DMA adapter that might be required before the start of each DMA transfer in a system-DMA-transmit transaction.
old-location: serports\evtsercx2systemdmatransmitconfiguredmachannel.htm
tech.root: serports
ms.assetid: F5748E93-9761-423B-9971-011FC4D7F6B8
ms.date: 04/23/2018
keywords: ["EVT_SERCX2_SYSTEM_DMA_TRANSMIT_CONFIGURE_DMA_CHANNEL callback function"]
ms.keywords: 2/EvtSerCx2SystemDmaTransmitConfigureDmaChannel, EVT_SERCX2_SYSTEM_DMA_TRANSMIT_CONFIGURE_DMA_CHANNEL, EVT_SERCX2_SYSTEM_DMA_TRANSMIT_CONFIGURE_DMA_CHANNEL callback, EvtSerCx2SystemDmaTransmitConfigureDmaChannel, EvtSerCx2SystemDmaTransmitConfigureDmaChannel callback function [Serial Ports], serports.evtsercx2systemdmatransmitconfiguredmachannel
f1_keywords:
 - "sercx/EvtSerCx2SystemDmaTransmitConfigureDmaChannel"
 - "EvtSerCx2SystemDmaTransmitConfigureDmaChannel"
req.header: sercx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8.1.
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
req.irql: Called at IRQL <= DISPATCH_LEVEL.
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- 2.0\Sercx.h
api_name:
- EvtSerCx2SystemDmaTransmitConfigureDmaChannel
targetos: Windows
req.typenames: 
---

# EVT_SERCX2_SYSTEM_DMA_TRANSMIT_CONFIGURE_DMA_CHANNEL callback function


## -description


The <i>EvtSerCx2SystemDmaTransmitConfigureDmaChannel</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to let the serial controller driver do any custom configuration of the DMA adapter that might be required before the start of each DMA transfer in a system-DMA-transmit transaction.


## -parameters




### -param SystemDmaTransmit [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMATRANSMIT</a> handle to a system-DMA-transmit object. The serial controller driver previously called the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmatransmitcreate">SerCx2SystemDmaTransmitCreate</a> method to create this object.


### -param Mdl [in]

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_mdl">MDL</a> that describes the memory pages that are spanned by the write buffer for the system-DMA-transmit transaction. The scatter/gather list for the DMA transfer will use the region of this memory that is specified by the <i>Offset</i> and <i>Length</i> parameters.


### -param Offset [in]

The starting offset for the data transfer. This parameter is a byte offset from the start of the buffer region described by the MDL. If the MDL specifies a total of N bytes of buffer space, possible values of <i>Offset</i> are in the range 0 to N–1.


### -param Length [in]

The size, in bytes, of the data transfer. If the MDL specifies a total of N bytes of buffer space, possible values of <i>Length</i> are in the range 1 to N–<i>Offset</i>.


## -returns



The <i>EvtSerCx2SystemDmaTransmitConfigureDmaChannel</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error status code.




## -remarks



Your serial controller driver can, as an option, implement this function. If implemented, the driver registers the function in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmatransmitcreate">SerCx2SystemDmaTransmitCreate</a> call that creates the system-DMA-transmit object.

Before initiating a system-DMA-transmit transaction, SerCx2 calls the <i>EvtSerCx2SystemDmaTransmitConfigureDmaChannel</i> function, if it is implemented. This function performs any special configuration of the system DMA controller that might be required before SerCx2 starts the system-DMA-transmit transaction.

The serial controller driver can call a method such as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmatransmitgetdmaenabler">SerCx2SystemDmaTransmitGetDmaEnabler</a> to get the DMA enabler for the system DMA controller used for system-DMA-transmit transactions.

For more information, see <a href="https://docs.microsoft.com/previous-versions/dn265338(v=vs.85)">SerCx2 System-DMA-Transmit Transactions</a>.


#### Examples

To define an <i>EvtSerCx2SystemDmaTransmitConfigureDmaChannel</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtSerCx2SystemDmaTransmitConfigureDmaChannel</i> callback function that is named <code>MySystemDmaTransmitConfigureDmaChannel</code>, use the <b>EVT_SERCX2_SYSTEM_DMA_TRANSMIT_CONFIGURE_DMA_CHANNEL</b> function type, as shown in this code example:

<div class="code"><span codelanguage="cpp"><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_SERCX2_SYSTEM_DMA_TRANSMIT_CONFIGURE_DMA_CHANNEL  MySystemDmaTransmitConfigureDmaChannel;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows:

<div class="code"><span codelanguage="cpp"><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
NTSTATUS
  MySystemDmaTransmitConfigureDmaChannel(
    SERCX2SYSTEMDMATRANSMIT SystemDmaTransmit,
    PMDL Mdl,
    ULONG Offset,
    ULONG Length
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_SERCX2_SYSTEM_DMA_TRANSMIT_CONFIGURE_DMA_CHANNEL</b> function type is defined in the Sercx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_SERCX2_SYSTEM_DMA_TRANSMIT_CONFIGURE_DMA_CHANNEL</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_mdl">MDL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMATRANSMIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmatransmitcreate">SerCx2SystemDmaTransmitCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2systemdmatransmitgetdmaenabler">SerCx2SystemDmaTransmitGetDmaEnabler</a>
 

 

