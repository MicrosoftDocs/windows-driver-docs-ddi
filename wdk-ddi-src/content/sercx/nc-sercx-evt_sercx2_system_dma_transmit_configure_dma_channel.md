---
UID: NC:sercx.EVT_SERCX2_SYSTEM_DMA_TRANSMIT_CONFIGURE_DMA_CHANNEL
title: EVT_SERCX2_SYSTEM_DMA_TRANSMIT_CONFIGURE_DMA_CHANNEL
author: windows-driver-content
description: The EvtSerCx2SystemDmaTransmitConfigureDmaChannel event callback function is called by version 2 of the serial framework extension (SerCx2) to let the serial controller driver do any custom configuration of the DMA adapter that might be required before the start of each DMA transfer in a system-DMA-transmit transaction.
old-location: serports\evtsercx2systemdmatransmitconfiguredmachannel.htm
old-project: serports
ms.assetid: F5748E93-9761-423B-9971-011FC4D7F6B8
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: serports.evtsercx2systemdmatransmitconfiguredmachannel, EvtSerCx2SystemDmaTransmitConfigureDmaChannel callback function [Serial Ports], EvtSerCx2SystemDmaTransmitConfigureDmaChannel, EVT_SERCX2_SYSTEM_DMA_TRANSMIT_CONFIGURE_DMA_CHANNEL, EVT_SERCX2_SYSTEM_DMA_TRANSMIT_CONFIGURE_DMA_CHANNEL, 2/EvtSerCx2SystemDmaTransmitConfigureDmaChannel
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	2.0\Sercx.h
apiname:
-	EvtSerCx2SystemDmaTransmitConfigureDmaChannel
product: Windows
targetos: Windows
req.typenames: SENSOR_VALUE_PAIR, *PSENSOR_VALUE_PAIR
req.product: Windows 10 or later.
---

# EVT_SERCX2_SYSTEM_DMA_TRANSMIT_CONFIGURE_DMA_CHANNEL callback


## -description


The <i>EvtSerCx2SystemDmaTransmitConfigureDmaChannel</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to let the serial controller driver do any custom configuration of the DMA adapter that might be required before the start of each DMA transfer in a system-DMA-transmit transaction.


## -prototype


````
EVT_SERCX2_SYSTEM_DMA_TRANSMIT_CONFIGURE_DMA_CHANNEL EvtSerCx2SystemDmaTransmitConfigureDmaChannel;

NTSTATUS EvtSerCx2SystemDmaTransmitConfigureDmaChannel(
  _In_ SERCX2SYSTEMDMATRANSMIT SystemDmaTransmit,
  _In_ PMDL                    Mdl,
  _In_ ULONG                   Offset,
  _In_ ULONG                   Length
)
{ ... }
````


## -parameters




### -param SystemDmaTransmit [in]

A <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMATRANSMIT</a> handle to a system-DMA-transmit object. The serial controller driver previously called the <a href="..\sercx\nf-sercx-sercx2systemdmatransmitcreate.md">SerCx2SystemDmaTransmitCreate</a> method to create this object.


### -param Mdl [in]

A pointer to an <a href="..\wdm\ns-wdm-_mdl.md">MDL</a> that describes the memory pages that are spanned by the write buffer for the system-DMA-transmit transaction. The scatter/gather list for the DMA transfer will use the region of this memory that is specified by the <i>Offset</i> and <i>Length</i> parameters.


### -param Offset [in]

The starting offset for the data transfer. This parameter is a byte offset from the start of the buffer region described by the MDL. If the MDL specifies a total of N bytes of buffer space, possible values of <i>Offset</i> are in the range 0 to N–1.


### -param Length [in]

The size, in bytes, of the data transfer. If the MDL specifies a total of N bytes of buffer space, possible values of <i>Length</i> are in the range 1 to N–<i>Offset</i>.


## -returns


The <i>EvtSerCx2SystemDmaTransmitConfigureDmaChannel</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error status code.



## -remarks


Your serial controller driver can, as an option, implement this function. If implemented, the driver registers the function in the <a href="..\sercx\nf-sercx-sercx2systemdmatransmitcreate.md">SerCx2SystemDmaTransmitCreate</a> call that creates the system-DMA-transmit object.

Before initiating a system-DMA-transmit transaction, SerCx2 calls the <i>EvtSerCx2SystemDmaTransmitConfigureDmaChannel</i> function, if it is implemented. This function performs any special configuration of the system DMA controller that might be required before SerCx2 starts the system-DMA-transmit transaction.

The serial controller driver can call a method such as <a href="..\sercx\nf-sercx-sercx2systemdmatransmitgetdmaenabler.md">SerCx2SystemDmaTransmitGetDmaEnabler</a> to get the DMA enabler for the system DMA controller used for system-DMA-transmit transactions.

For more information, see <a href="https://msdn.microsoft.com/8569E76F-CAFF-4A2C-8052-62B340C5ADED">SerCx2 System-DMA-Transmit Transactions</a>.



## -see-also

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMATRANSMIT</a>

<a href="..\sercx\nf-sercx-sercx2systemdmatransmitcreate.md">SerCx2SystemDmaTransmitCreate</a>

<a href="..\wdm\ns-wdm-_mdl.md">MDL</a>

<a href="..\sercx\nf-sercx-sercx2systemdmatransmitgetdmaenabler.md">SerCx2SystemDmaTransmitGetDmaEnabler</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20EVT_SERCX2_SYSTEM_DMA_TRANSMIT_CONFIGURE_DMA_CHANNEL callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

