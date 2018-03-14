---
UID: NF:sercx.SerCx2SystemDmaReceiveCleanupTransactionComplete
title: SerCx2SystemDmaReceiveCleanupTransactionComplete function
author: windows-driver-content
description: The SerCx2SystemDmaReceiveCleanupTransactionComplete method notifies version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished cleaning up the serial controller's hardware state after a system-DMA-receive transaction.
old-location: serports\sercx2systemdmareceivecleanuptransactioncomplete.htm
old-project: serports
ms.assetid: B56FEA86-E171-43DA-8207-148298E72313
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: 2/SerCx2SystemDmaReceiveCleanupTransactionComplete, SerCx2SystemDmaReceiveCleanupTransactionComplete, SerCx2SystemDmaReceiveCleanupTransactionComplete method [Serial Ports], serports.sercx2systemdmareceivecleanuptransactioncomplete
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
req.lib: 
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	2.0\Sercx.h
api_name:
-	SerCx2SystemDmaReceiveCleanupTransactionComplete
product: Windows
targetos: Windows
req.typenames: SERCX_STATUS, *PSERCX_STATUS
req.product: Windows 10 or later.
---

# SerCx2SystemDmaReceiveCleanupTransactionComplete function


## -description


The <b>SerCx2SystemDmaReceiveCleanupTransactionComplete</b> method notifies version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished cleaning up the serial controller's hardware state after a system-DMA-receive transaction.


## -syntax


````
VOID SerCx2SystemDmaReceiveCleanupTransactionComplete(
  [in] SERCX2SYSTEMDMARECEIVE SystemDmaReceive
);
````


## -parameters




### -param SystemDmaReceive [in]

A <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMARECEIVE</a> handle to a system-DMA-receive object. The serial controller driver previously called the <a href="..\sercx\nf-sercx-sercx2systemdmareceivecreate.md">SerCx2SystemDmaReceiveCreate</a> method to create this object.


## -returns



None.




## -remarks



After a system-DMA-receive transaction ends, SerCx2 calls the <a href="..\sercx\nc-sercx-evt_sercx2_system_dma_receive_cleanup_transaction.md">EvtSerCx2SystemDmaReceiveCleanupTransaction</a> event callback function, if it is implemented, to clean up the serial controller state. In response to this call, the driver should do any clean-up work that is needed; then the driver must call <b>SerCx2SystemDmaReceiveCleanupTransactionComplete</b> to notify SerCx2. SerCx2 expects this notification and does not start the next transaction until it is notified.

The serial controller driver must call <b>SerCx2SystemDmaReceiveCleanupTransactionComplete</b> only in response to a call to the <i>EvtSerCx2SystemDmaReceiveCleanupTransaction</i> function.

For more information, see <a href="https://msdn.microsoft.com/0374D1BE-96ED-43D6-8661-5E9676B82C0D">SerCx2 System-DMA-Receive Transaction</a>.




## -see-also

<a href="..\sercx\nf-sercx-sercx2systemdmareceivecreate.md">SerCx2SystemDmaReceiveCreate</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMARECEIVE</a>



<a href="..\sercx\nc-sercx-evt_sercx2_system_dma_receive_cleanup_transaction.md">EvtSerCx2SystemDmaReceiveCleanupTransaction</a>



 

 


