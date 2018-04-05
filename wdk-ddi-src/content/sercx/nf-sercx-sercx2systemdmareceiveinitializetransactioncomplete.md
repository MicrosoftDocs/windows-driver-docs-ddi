---
UID: NF:sercx.SerCx2SystemDmaReceiveInitializeTransactionComplete
title: SerCx2SystemDmaReceiveInitializeTransactionComplete function
author: windows-driver-content
description: The SerCx2SystemDmaReceiveInitializeTransactionComplete method notifies version 2 of the serial framework extension (SerCx2) that the serial driver has finished initializing the serial controller hardware in preparation for a new system-DMA-receive transaction.
old-location: serports\sercx2systemdmareceiveinitializetransactioncomplete.htm
old-project: serports
ms.assetid: B65DC4AD-FB24-4F1D-A1E9-F9B38160908E
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: 2/SerCx2SystemDmaReceiveInitializeTransactionComplete, SerCx2SystemDmaReceiveInitializeTransactionComplete, SerCx2SystemDmaReceiveInitializeTransactionComplete method [Serial Ports], serports.sercx2systemdmareceiveinitializetransactioncomplete
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
-	SerCx2SystemDmaReceiveInitializeTransactionComplete
product:
- Windows
targetos: Windows
req.typenames: SERCX_STATUS, *PSERCX_STATUS
req.product: Windows 10 or later.
---

# SerCx2SystemDmaReceiveInitializeTransactionComplete function


## -description


The <b>SerCx2SystemDmaReceiveInitializeTransactionComplete</b> method notifies version 2 of the serial framework extension (SerCx2) that the serial driver has finished initializing the serial controller hardware in preparation for a new system-DMA-receive transaction.


## -parameters




### -param SystemDmaReceive [in]

A <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMARECEIVE</a> handle to a system-DMA-receive object. The serial controller driver previously called the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265279">SerCx2SystemDmaReceiveCreate</a> method to create this object.


### -param InitSuccess [in]

Whether the initialization was successful. If <b>TRUE</b>, the initialization succeeded. If <b>FALSE</b>, the initialization failed.


## -returns



None.




## -remarks



Before SerCx2 initiates a system-DMA-receive transaction, SerCx2 calls the <a href="https://msdn.microsoft.com/34E016AF-439C-44CC-A2AE-78CD7B2B5443">EvtSerCx2SystemDmaReceiveInitializeTransaction</a> event callback function, if it is implemented, to initialize the serial controller to perform the transaction. In response to this call, the driver should do any initialization that is needed; then the driver must call <b>SerCx2SystemDmaReceiveInitializeTransactionComplete</b> to notify SerCx2. SerCx2 expects this notification and does not start the transaction until it is notified.

The serial controller driver must call <b>SerCx2SystemDmaReceiveInitializeTransactionComplete</b> only in response to a call to the <a href="https://msdn.microsoft.com/34E016AF-439C-44CC-A2AE-78CD7B2B5443">EvtSerCx2SystemDmaReceiveInitializeTransaction</a> function.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn265343">SerCx2 System-DMA-Receive Transactions</a>.




## -see-also




<a href="https://msdn.microsoft.com/34E016AF-439C-44CC-A2AE-78CD7B2B5443">EvtSerCx2SystemDmaReceiveInitializeTransaction</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMARECEIVE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265279">SerCx2SystemDmaReceiveCreate</a>
 

 

