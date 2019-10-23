---
UID: NF:sercx.SerCx2PioReceiveCleanupTransactionComplete
title: SerCx2PioReceiveCleanupTransactionComplete function (sercx.h)
description: The SerCx2PioReceiveCleanupTransactionComplete method informs version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished cleaning up the serial controller's hardware state after a PIO-receive transaction.
old-location: serports\sercx2pioreceivecleanuptransactioncomplete.htm
tech.root: serports
ms.assetid: 8C0874CD-EAFD-4443-B394-AAA4DD265835
ms.date: 04/23/2018
ms.keywords: 2/SerCx2PioReceiveCleanupTransactionComplete, SerCx2PioReceiveCleanupTransactionComplete, SerCx2PioReceiveCleanupTransactionComplete method [Serial Ports], serports.sercx2pioreceivecleanuptransactioncomplete
ms.topic: function
f1_keywords:
 - "sercx/SerCx2PioReceiveCleanupTransactionComplete"
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- 2.0\Sercx.h
api_name:
- SerCx2PioReceiveCleanupTransactionComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# SerCx2PioReceiveCleanupTransactionComplete function


## -description


The <b>SerCx2PioReceiveCleanupTransactionComplete</b> method informs version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished cleaning up the serial controller's hardware state after a PIO-receive transaction.


## -parameters




### -param PioReceive [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIORECEIVE</a> handle to a PIO-receive object. The serial controller driver previously called the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2pioreceivecreate">SerCx2PioReceiveCreate</a> method to create this object.


## -returns



None.




## -remarks



After a PIO-receive transaction ends, SerCx2 calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_receive_cleanup_transaction">EvtSerCx2PioReceiveCleanupTransaction</a> event callback function, if it is implemented, to clean up the serial controller state. In response to this call, the driver should first do any clean-up work that is needed; then the driver must call <b>SerCx2PioReceiveCleanupTransactionComplete</b> to notify SerCx2. SerCx2 expects this notification and does not start the next transaction until it is notified.

The serial controller driver must call <b>SerCx2PioReceiveCleanupTransactionComplete</b> only in response to a call to the <i>EvtSerCx2PioReceiveCleanupTransaction</i> function.

For more information, see <a href="https://docs.microsoft.com/previous-versions/dn265332(v=vs.85)">SerCx2 PIO-Receive Transactions</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_pio_receive_cleanup_transaction">EvtSerCx2PioReceiveCleanupTransaction</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIORECEIVE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2pioreceivecreate">SerCx2PioReceiveCreate</a>
 

 

