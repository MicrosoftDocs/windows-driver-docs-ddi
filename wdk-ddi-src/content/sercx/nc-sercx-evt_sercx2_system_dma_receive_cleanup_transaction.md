---
UID: NC:sercx.EVT_SERCX2_SYSTEM_DMA_RECEIVE_CLEANUP_TRANSACTION
title: EVT_SERCX2_SYSTEM_DMA_RECEIVE_CLEANUP_TRANSACTION
author: windows-driver-content
description: The EvtSerCx2SystemDmaReceiveCleanupTransaction event callback function is called by version 2 of the serial framework extension (SerCx2) to clean up the serial controller state after a system-DMA-receive transaction ends.
old-location: serports\evtsercx2systemdmareceivecleanuptransaction.htm
old-project: serports
ms.assetid: 66B15ED1-583D-418C-90C5-25BBBCEE7B5A
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: serports.evtsercx2systemdmareceivecleanuptransaction, EvtSerCx2SystemDmaReceiveCleanupTransaction callback function [Serial Ports], EvtSerCx2SystemDmaReceiveCleanupTransaction, EVT_SERCX2_SYSTEM_DMA_RECEIVE_CLEANUP_TRANSACTION, EVT_SERCX2_SYSTEM_DMA_RECEIVE_CLEANUP_TRANSACTION, 2/EvtSerCx2SystemDmaReceiveCleanupTransaction
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
-	EvtSerCx2SystemDmaReceiveCleanupTransaction
product: Windows
targetos: Windows
req.typenames: SENSOR_VALUE_PAIR, *PSENSOR_VALUE_PAIR
req.product: Windows 10 or later.
---

# EVT_SERCX2_SYSTEM_DMA_RECEIVE_CLEANUP_TRANSACTION callback


## -description


The <i>EvtSerCx2SystemDmaReceiveCleanupTransaction</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to clean up the serial controller state after a system-DMA-receive transaction ends.


## -prototype


````
EVT_SERCX2_SYSTEM_DMA_RECEIVE_CLEANUP_TRANSACTION EvtSerCx2SystemDmaReceiveCleanupTransaction;

VOID EvtSerCx2SystemDmaReceiveCleanupTransaction(
  _In_ SERCX2SYSTEMDMARECEIVE SystemDmaReceive
)
{ ... }
````


## -parameters




#### - SystemDmaReceive [in]

A <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMARECEIVE</a> handle to a system-DMA-receive object. The serial controller driver previously called the <a href="..\sercx\nf-sercx-sercx2systemdmareceivecreate.md">SerCx2SystemDmaReceiveCreate</a> method to create this object.


## -returns


None.



## -remarks


Your serial controller driver can, as an option, implement this function. If implemented, the driver registers the function in the <a href="..\sercx\nf-sercx-sercx2systemdmareceivecreate.md">SerCx2SystemDmaReceiveCreate</a> call that creates the system-DMA-receive object.

Your serial controller driver should implement an <i>EvtSerCx2SystemDmaReceiveCleanupTransaction</i> function if it needs to clean up the serial controller state at the end of a system-DMA-receive transaction. SerCx2 calls this function, if it is implemented, after a system-DMA-receive transaction ends. In response to the <i>EvtSerCx2SystemDmaReceiveCleanupTransaction</i> call, the serial controller driver must call the <a href="..\sercx\nf-sercx-sercx2systemdmareceivecleanuptransactioncomplete.md">SerCx2SystemDmaReceiveCleanupTransactionComplete</a> method to notify SerCx2 after the clean-up work is done.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn265343">SerCx2 System-DMA-Receive Transactions</a>.



## -see-also

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMARECEIVE</a>

<a href="..\sercx\nf-sercx-sercx2systemdmareceivecleanuptransactioncomplete.md">SerCx2SystemDmaReceiveCleanupTransactionComplete</a>

<a href="..\sercx\nf-sercx-sercx2systemdmareceivecreate.md">SerCx2SystemDmaReceiveCreate</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20EVT_SERCX2_SYSTEM_DMA_RECEIVE_CLEANUP_TRANSACTION callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

