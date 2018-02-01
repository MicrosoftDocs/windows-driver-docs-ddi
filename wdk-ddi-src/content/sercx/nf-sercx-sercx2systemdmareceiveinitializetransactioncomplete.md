---
UID: NF:sercx.SerCx2SystemDmaReceiveInitializeTransactionComplete
title: SerCx2SystemDmaReceiveInitializeTransactionComplete function
author: windows-driver-content
description: The SerCx2SystemDmaReceiveInitializeTransactionComplete method notifies version 2 of the serial framework extension (SerCx2) that the serial driver has finished initializing the serial controller hardware in preparation for a new system-DMA-receive transaction.
old-location: serports\sercx2systemdmareceiveinitializetransactioncomplete.htm
old-project: serports
ms.assetid: B65DC4AD-FB24-4F1D-A1E9-F9B38160908E
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SerCx2SystemDmaReceiveInitializeTransactionComplete, serports.sercx2systemdmareceiveinitializetransactioncomplete, SerCx2SystemDmaReceiveInitializeTransactionComplete method [Serial Ports], 2/SerCx2SystemDmaReceiveInitializeTransactionComplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: sercx.h
req.include-header: 
req.target-type: Universal
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	2.0\Sercx.h
apiname:
-	SerCx2SystemDmaReceiveInitializeTransactionComplete
product: Windows
targetos: Windows
req.typenames: "*PSERCX_STATUS, SERCX_STATUS"
req.product: Windows 10 or later.
---

# SerCx2SystemDmaReceiveInitializeTransactionComplete function


## -description


The <b>SerCx2SystemDmaReceiveInitializeTransactionComplete</b> method notifies version 2 of the serial framework extension (SerCx2) that the serial driver has finished initializing the serial controller hardware in preparation for a new system-DMA-receive transaction.


## -syntax


````
VOID SerCx2SystemDmaReceiveInitializeTransactionComplete(
  [in] SERCX2SYSTEMDMARECEIVE SystemDmaReceive,
  [in] BOOLEAN                InitSuccess
);
````


## -parameters




### -param SystemDmaReceive [in]

A <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMARECEIVE</a> handle to a system-DMA-receive object. The serial controller driver previously called the <a href="..\sercx\nf-sercx-sercx2systemdmareceivecreate.md">SerCx2SystemDmaReceiveCreate</a> method to create this object.


### -param InitSuccess [in]

Whether the initialization was successful. If <b>TRUE</b>, the initialization succeeded. If <b>FALSE</b>, the initialization failed.


## -returns


None.



## -remarks


Before SerCx2 initiates a system-DMA-receive transaction, SerCx2 calls the <a href="..\sercx\nc-sercx-evt_sercx2_system_dma_receive_initialize_transaction.md">EvtSerCx2SystemDmaReceiveInitializeTransaction</a> event callback function, if it is implemented, to initialize the serial controller to perform the transaction. In response to this call, the driver should do any initialization that is needed; then the driver must call <b>SerCx2SystemDmaReceiveInitializeTransactionComplete</b> to notify SerCx2. SerCx2 expects this notification and does not start the transaction until it is notified.

The serial controller driver must call <b>SerCx2SystemDmaReceiveInitializeTransactionComplete</b> only in response to a call to the <a href="..\sercx\nc-sercx-evt_sercx2_system_dma_receive_initialize_transaction.md">EvtSerCx2SystemDmaReceiveInitializeTransaction</a> function.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn265343">SerCx2 System-DMA-Receive Transactions</a>.



## -see-also

<a href="..\sercx\nc-sercx-evt_sercx2_system_dma_receive_initialize_transaction.md">EvtSerCx2SystemDmaReceiveInitializeTransaction</a>

<a href="..\sercx\nf-sercx-sercx2systemdmareceivecreate.md">SerCx2SystemDmaReceiveCreate</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMARECEIVE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SerCx2SystemDmaReceiveInitializeTransactionComplete method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

