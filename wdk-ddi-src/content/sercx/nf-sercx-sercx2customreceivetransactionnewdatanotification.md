---
UID: NF:sercx.SerCx2CustomReceiveTransactionNewDataNotification
title: SerCx2CustomReceiveTransactionNewDataNotification function (sercx.h)
description: The SerCx2CustomReceiveTransactionNewDataNotification method notifies version 2 of the serial framework extension (SerCx2) that data is available to be read from the receive FIFO in the serial controller hardware.
old-location: serports\sercx2customreceivetransactionnewdatanotification.htm
tech.root: serports
ms.assetid: 181B2619-A8A8-45ED-935B-B4F12A0695E0
ms.date: 04/23/2018
keywords: ["SerCx2CustomReceiveTransactionNewDataNotification function"]
ms.keywords: 2/SerCx2CustomReceiveTransactionNewDataNotification, SerCx2CustomReceiveTransactionNewDataNotification, SerCx2CustomReceiveTransactionNewDataNotification method [Serial Ports], serports.sercx2customreceivetransactionnewdatanotification
f1_keywords:
 - "sercx/SerCx2CustomReceiveTransactionNewDataNotification"
 - "SerCx2CustomReceiveTransactionNewDataNotification"
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
- SerCx2CustomReceiveTransactionNewDataNotification
targetos: Windows
req.typenames: 
---

# SerCx2CustomReceiveTransactionNewDataNotification function


## -description


The <b>SerCx2CustomReceiveTransactionNewDataNotification</b> method notifies version 2 of the serial framework extension (SerCx2) that data is available to be read from the receive FIFO in the serial controller hardware.


## -parameters




### -param CustomReceiveTransaction [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2CUSTOMRECEIVETRANSACTION</a> handle to a custom-receive object. The serial controller driver previously called the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2customreceivetransactioncreate">SerCx2CustomReceiveTransactionCreate</a> method to create this object.


## -remarks



If the receive FIFO in the serial controller becomes empty before a custom-receive transaction can be completed, SerCx2 calls the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/dn265201(v=vs.85)">EvtSerCx2CustomReceiveTransactionEnableNewDataNotification</a> event callback function, if it is implemented, to enable a new-data notification to occur when new data is available to be read from the receive FIFO.

If new-data notifications are enabled and new data is available to be read, the serial controller driver must call <b>SerCx2CustomReceiveTransactionNewDataNotification</b> to notify SerCx2. This notification occurs when the driver detects that one or more new bytes of received data either are ready to be transferred by the custom data-transfer mechanism or have already been transferred by this mechanism.

The serial controller driver must call <b>SerCx2CustomReceiveTransactionNewDataNotification</b> only in response to a call to the <i>EvtSerCx2CustomReceiveTransactionEnableNewDataNotification</i> function.

If a serial controller driver supports new-data notifications for custom-receive transactions, SerCx uses these notifications to detect interval time-outs during the handling of read (<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-read">IRP_MJ_READ</a>) requests. For more information about interval time-outs, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ns-ntddser-_serial_timeouts">SERIAL_TIMEOUTS</a>. For more information about new-data notifications, see <a href="https://docs.microsoft.com/previous-versions/dn265314(v=vs.85)">SerCx2 Custom-Receive Transactions</a>.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/dn265201(v=vs.85)">EvtSerCx2CustomReceiveTransactionEnableNewDataNotification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-read">IRP_MJ_READ</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2CUSTOMRECEIVETRANSACTION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ns-ntddser-_serial_timeouts">SERIAL_TIMEOUTS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2customreceivetransactioncreate">SerCx2CustomReceiveTransactionCreate</a>
 

 

