---
UID: NF:sercx.SerCx2PioReceiveCleanupTransactionComplete
title: SerCx2PioReceiveCleanupTransactionComplete function
author: windows-driver-content
description: The SerCx2PioReceiveCleanupTransactionComplete method informs version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished cleaning up the serial controller's hardware state after a PIO-receive transaction.
old-location: serports\sercx2pioreceivecleanuptransactioncomplete.htm
old-project: serports
ms.assetid: 8C0874CD-EAFD-4443-B394-AAA4DD265835
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: 2/SerCx2PioReceiveCleanupTransactionComplete, serports.sercx2pioreceivecleanuptransactioncomplete, SerCx2PioReceiveCleanupTransactionComplete method [Serial Ports], SerCx2PioReceiveCleanupTransactionComplete
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
-	SerCx2PioReceiveCleanupTransactionComplete
product: Windows
targetos: Windows
req.typenames: SERCX_STATUS, *PSERCX_STATUS
req.product: Windows 10 or later.
---

# SerCx2PioReceiveCleanupTransactionComplete function


## -description


The <b>SerCx2PioReceiveCleanupTransactionComplete</b> method informs version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished cleaning up the serial controller's hardware state after a PIO-receive transaction.


## -syntax


````
VOID SerCx2PioReceiveCleanupTransactionComplete(
  [in] SERCX2PIORECEIVE PioReceive
);
````


## -parameters




### -param PioReceive [in]

A <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIORECEIVE</a> handle to a PIO-receive object. The serial controller driver previously called the <a href="..\sercx\nf-sercx-sercx2pioreceivecreate.md">SerCx2PioReceiveCreate</a> method to create this object.


## -returns



None.




## -remarks



After a PIO-receive transaction ends, SerCx2 calls the <a href="..\sercx\nc-sercx-evt_sercx2_pio_receive_cleanup_transaction.md">EvtSerCx2PioReceiveCleanupTransaction</a> event callback function, if it is implemented, to clean up the serial controller state. In response to this call, the driver should first do any clean-up work that is needed; then the driver must call <b>SerCx2PioReceiveCleanupTransactionComplete</b> to notify SerCx2. SerCx2 expects this notification and does not start the next transaction until it is notified.

The serial controller driver must call <b>SerCx2PioReceiveCleanupTransactionComplete</b> only in response to a call to the <i>EvtSerCx2PioReceiveCleanupTransaction</i> function.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn265332">SerCx2 PIO-Receive Transactions</a>.




## -see-also

<a href="..\sercx\nf-sercx-sercx2pioreceivecreate.md">SerCx2PioReceiveCreate</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIORECEIVE</a>



<a href="..\sercx\nc-sercx-evt_sercx2_pio_receive_cleanup_transaction.md">EvtSerCx2PioReceiveCleanupTransaction</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SerCx2PioReceiveCleanupTransactionComplete method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

