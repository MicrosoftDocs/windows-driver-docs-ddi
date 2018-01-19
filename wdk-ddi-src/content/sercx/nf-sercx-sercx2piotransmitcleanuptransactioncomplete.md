---
UID: NF:sercx.SerCx2PioTransmitCleanupTransactionComplete
title: SerCx2PioTransmitCleanupTransactionComplete function
author: windows-driver-content
description: The SerCx2PioTransmitCleanupTransactionComplete method notifies version 2 of the serial framework extension (SerCx2) that serial controller driver has finished cleaning up the serial controller's hardware state after a PIO-transmit transaction.
old-location: serports\sercx2piotransmitcleanuptransactioncomplete.htm
old-project: serports
ms.assetid: 44ADAAB7-E0EE-4908-A0D8-366EC1C3AC2E
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SerCx2PioTransmitCleanupTransactionComplete
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
req.alt-api: SerCx2PioTransmitCleanupTransactionComplete
req.alt-loc: 2.0\Sercx.h
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
req.typenames: SERCX_STATUS, *PSERCX_STATUS
req.product: Windows 10 or later.
---

# SerCx2PioTransmitCleanupTransactionComplete function



## -description
The <b>SerCx2PioTransmitCleanupTransactionComplete</b> method notifies version 2 of the serial framework extension (SerCx2) that serial controller driver has finished cleaning up the serial controller's hardware state after a PIO-transmit transaction.



## -syntax

````
VOID SerCx2PioTransmitCleanupTransactionComplete(
  [in] SERCX2PIOTRANSMIT PioTransmit
);
````


## -parameters

### -param PioTransmit [in]

A <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIOTRANSMIT</a> handle to a PIO-transmit object. The serial controller driver previously called the <a href="..\sercx\nf-sercx-sercx2piotransmitcreate.md">SerCx2PioTransmitCreate</a> method to create this object.


## -returns
None.


## -remarks
After a PIO-transmit transaction ends, SerCx2 calls the <a href="..\sercx\nc-sercx-evt_sercx2_pio_transmit_cleanup_transaction.md">EvtSerCx2PioTransmitCleanupTransaction</a> event callback function, if it is implemented, to clean up the serial controller state. In response to this call, the driver should first do any clean-up work that is needed; then the driver must call <b>SerCx2PioTransmitCleanupTransactionComplete</b> to notify SerCx2. SerCx2 waits for this notification to start the next transaction.

The serial must call <b>SerCx2PioTransmitCleanupTransactionComplete</b> only in response to a call to the <i>EvtSerCx2PioTransmitCleanupTransaction</i> function.

For more information, see <a href="https://msdn.microsoft.com/3BEF9A3D-1FEF-4626-B07F-1670359062AF">SerCx2 PIO-Transmit Transactions</a>.


## -see-also
<dl>
<dt>
<a href="..\sercx\nc-sercx-evt_sercx2_pio_transmit_cleanup_transaction.md">EvtSerCx2PioTransmitCleanupTransaction</a>
</dt>
<dt>
<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIOTRANSMIT</a>
</dt>
<dt>
<a href="..\sercx\nf-sercx-sercx2piotransmitcreate.md">SerCx2PioTransmitCreate</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SerCx2PioTransmitCleanupTransactionComplete method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

