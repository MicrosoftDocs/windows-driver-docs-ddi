---
UID: NF:sercx.SerCx2SystemDmaReceiveNewDataNotification
title: SerCx2SystemDmaReceiveNewDataNotification function
author: windows-driver-content
description: The SerCx2SystemDmaReceiveNewDataNotification method notifies version 2 of the serial framework extension (SerCx2) that data is available to be read from the receive FIFO in the serial controller hardware.
old-location: serports\sercx2systemdmareceivenewdatanotification.htm
old-project: serports
ms.assetid: 9ECC15F2-9D08-4EEF-ADBD-612D8D1B5B72
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: SerCx2SystemDmaReceiveNewDataNotification, serports.sercx2systemdmareceivenewdatanotification, SerCx2SystemDmaReceiveNewDataNotification method [Serial Ports], 2/SerCx2SystemDmaReceiveNewDataNotification
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
-	SerCx2SystemDmaReceiveNewDataNotification
product: Windows
targetos: Windows
req.typenames: SERCX_STATUS, *PSERCX_STATUS
req.product: Windows 10 or later.
---

# SerCx2SystemDmaReceiveNewDataNotification function


## -description


The <b>SerCx2SystemDmaReceiveNewDataNotification</b> method notifies version 2 of the serial framework extension (SerCx2) that data is available to be read from the receive FIFO in the serial controller hardware.


## -syntax


````
VOID SerCx2SystemDmaReceiveNewDataNotification(
  [in] SERCX2SYSTEMDMARECEIVE SystemDmaReceive
);
````


## -parameters




### -param SystemDmaReceive [in]

A <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMARECEIVE</a> handle to a system-DMA-receive object. The serial controller driver previously called the <a href="..\sercx\nf-sercx-sercx2systemdmareceivecreate.md">SerCx2SystemDmaReceiveCreate</a> method to create this object.


## -returns



None.




## -remarks



If the receive FIFO in the serial controller becomes empty before a system-DMA-receive transaction can be completed, SerCx2 calls the <a href="..\sercx\nc-sercx-evt_sercx2_system_dma_receive_enable_new_data_notification.md">EvtSerCx2SystemDmaReceiveEnableNewDataNotification</a> event callback function, if it is implemented, to enable SerCx2 to receive a new-data notification when data is again available to be read from the receive FIFO.

If the new-data notification is enabled, the serial controller driver must call <b>SerCx2SystemDmaReceiveNewDataNotification</b> to notify SerCx2 after the serial controller receives new data. A notification occurs when the driver detects that one or more new bytes of received data either are ready to be transferred or have already been transferred by the system DMA controller.

The serial controller must call <b>SerCx2SystemDmaReceiveNewDataNotification</b> only in response to a call to the <i>EvtSerCx2SystemDmaReceiveEnableNewDataNotification</i> function.

If a serial controller driver supports new-data notifications for system-DMA-receive transactions, SerCx uses these notifications to detect interval time-outs during the handling of read (<a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a>) requests. For more information about interval time-outs, see <a href="..\ntddser\ns-ntddser-_serial_timeouts.md">SERIAL_TIMEOUTS</a>. For more information about new-data notifications, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn265343">SerCx2 System-DMA-Receive Transactions</a>.




## -see-also

<a href="..\sercx\nc-sercx-evt_sercx2_system_dma_receive_enable_new_data_notification.md">EvtSerCx2SystemDmaReceiveEnableNewDataNotification</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMARECEIVE</a>



<a href="..\ntddser\ns-ntddser-_serial_timeouts.md">SERIAL_TIMEOUTS</a>



<a href="..\sercx\nf-sercx-sercx2systemdmareceivecreate.md">SerCx2SystemDmaReceiveCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SerCx2SystemDmaReceiveNewDataNotification method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

