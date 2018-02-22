---
UID: NF:sercx.SerCx2CustomReceiveTransactionNewDataNotification
title: SerCx2CustomReceiveTransactionNewDataNotification function
author: windows-driver-content
description: The SerCx2CustomReceiveTransactionNewDataNotification method notifies version 2 of the serial framework extension (SerCx2) that data is available to be read from the receive FIFO in the serial controller hardware.
old-location: serports\sercx2customreceivetransactionnewdatanotification.htm
old-project: serports
ms.assetid: 181B2619-A8A8-45ED-935B-B4F12A0695E0
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: serports.sercx2customreceivetransactionnewdatanotification, SerCx2CustomReceiveTransactionNewDataNotification, SerCx2CustomReceiveTransactionNewDataNotification method [Serial Ports], 2/SerCx2CustomReceiveTransactionNewDataNotification
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
-	SerCx2CustomReceiveTransactionNewDataNotification
product: Windows
targetos: Windows
req.typenames: "*PSERCX_STATUS, SERCX_STATUS"
req.product: Windows 10 or later.
---

# SerCx2CustomReceiveTransactionNewDataNotification function


## -description


The <b>SerCx2CustomReceiveTransactionNewDataNotification</b> method notifies version 2 of the serial framework extension (SerCx2) that data is available to be read from the receive FIFO in the serial controller hardware.


## -syntax


````
VOID SerCx2CustomReceiveTransactionNewDataNotification(
  [in] SERCX2CUSTOMRECEIVETRANSACTION CustomReceiveTransaction
);
````


## -parameters




### -param CustomReceiveTransaction [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/dn265249">SERCX2CUSTOMRECEIVETRANSACTION</a> handle to a custom-receive object. The serial controller driver previously called the <a href="..\sercx\nf-sercx-sercx2customreceivetransactioncreate.md">SerCx2CustomReceiveTransactionCreate</a> method to create this object.


## -returns



None.




## -remarks



If the receive FIFO in the serial controller becomes empty before a custom-receive transaction can be completed, SerCx2 calls the <a href="https://msdn.microsoft.com/C3E446AB-17AA-4FD8-8245-16D95134B0E7">EvtSerCx2CustomReceiveTransactionEnableNewDataNotification</a> event callback function, if it is implemented, to enable a new-data notification to occur when new data is available to be read from the receive FIFO.

If new-data notifications are enabled and new data is available to be read, the serial controller driver must call <b>SerCx2CustomReceiveTransactionNewDataNotification</b> to notify SerCx2. This notification occurs when the driver detects that one or more new bytes of received data either are ready to be transferred by the custom data-transfer mechanism or have already been transferred by this mechanism.

The serial controller driver must call <b>SerCx2CustomReceiveTransactionNewDataNotification</b> only in response to a call to the <i>EvtSerCx2CustomReceiveTransactionEnableNewDataNotification</i> function.

If a serial controller driver supports new-data notifications for custom-receive transactions, SerCx uses these notifications to detect interval time-outs during the handling of read (<a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a>) requests. For more information about interval time-outs, see <a href="..\ntddser\ns-ntddser-_serial_timeouts.md">SERIAL_TIMEOUTS</a>. For more information about new-data notifications, see <a href="https://msdn.microsoft.com/29849A8C-6656-444C-BE91-405A4BA2D5B0">SerCx2 Custom-Receive Transactions</a>.




## -see-also

<a href="..\ntddser\ns-ntddser-_serial_timeouts.md">SERIAL_TIMEOUTS</a>



<a href="https://msdn.microsoft.com/C3E446AB-17AA-4FD8-8245-16D95134B0E7">EvtSerCx2CustomReceiveTransactionEnableNewDataNotification</a>



<a href="..\sercx\nf-sercx-sercx2customreceivetransactioncreate.md">SerCx2CustomReceiveTransactionCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265249">SERCX2CUSTOMRECEIVETRANSACTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SerCx2CustomReceiveTransactionNewDataNotification method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

