---
UID: NC:sercx.EVT_SERCX2_SYSTEM_DMA_RECEIVE_ENABLE_NEW_DATA_NOTIFICATION
title: EVT_SERCX2_SYSTEM_DMA_RECEIVE_ENABLE_NEW_DATA_NOTIFICATION
author: windows-driver-content
description: The EvtSerCx2SystemDmaReceiveEnableNewDataNotification event callback function is called by version 2 of the serial framework extension (SerCx2) to enable the serial controller driver to notify SerCx2 when the serial controller receives new data.
old-location: serports\evtsercx2systemdmareceiveenablenewdatanotification.htm
old-project: serports
ms.assetid: E2B7FE14-1D06-48E7-95FB-C103358340EA
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: serports.evtsercx2systemdmareceiveenablenewdatanotification, EvtSerCx2SystemDmaReceiveEnableNewDataNotification callback function [Serial Ports], EvtSerCx2SystemDmaReceiveEnableNewDataNotification, EVT_SERCX2_SYSTEM_DMA_RECEIVE_ENABLE_NEW_DATA_NOTIFICATION, EVT_SERCX2_SYSTEM_DMA_RECEIVE_ENABLE_NEW_DATA_NOTIFICATION, 2/EvtSerCx2SystemDmaReceiveEnableNewDataNotification
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
-	EvtSerCx2SystemDmaReceiveEnableNewDataNotification
product: Windows
targetos: Windows
req.typenames: SENSOR_VALUE_PAIR, *PSENSOR_VALUE_PAIR
req.product: Windows 10 or later.
---

# EVT_SERCX2_SYSTEM_DMA_RECEIVE_ENABLE_NEW_DATA_NOTIFICATION callback


## -description


The <i>EvtSerCx2SystemDmaReceiveEnableNewDataNotification</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to enable the serial controller driver to notify SerCx2 when the serial controller receives new data.


## -prototype


````
EVT_SERCX2_SYSTEM_DMA_RECEIVE_ENABLE_NEW_DATA_NOTIFICATION EvtSerCx2SystemDmaReceiveEnableNewDataNotification;

VOID EvtSerCx2SystemDmaReceiveEnableNewDataNotification(
  _In_ SERCX2SYSTEMDMARECEIVE SystemDmaReceive
)
{ ... }
````


## -parameters




### -param SystemDmaReceive [in]

A <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMARECEIVE</a> handle to a system-DMA-receive object. The serial controller driver previously called the <a href="..\sercx\nf-sercx-sercx2systemdmareceivecreate.md">SerCx2SystemDmaReceiveCreate</a> method to create this object.


## -returns


None.



## -remarks


Your serial controller driver can, as an option, implement this function. If implemented, the driver registers the function in the <a href="..\sercx\nf-sercx-sercx2systemdmareceivecreate.md">SerCx2SystemDmaReceiveCreate</a> call that creates the system-DMA-receive object.

After the <i>EvtSerCx2SystemDmaReceiveEnableNewDataNotification</i> function is called to enable a new-data notification for a system-DMA-receive transaction, the serial controller driver must call the <a href="..\sercx\nf-sercx-sercx2systemdmareceivenewdatanotification.md">SerCx2SystemDmaReceiveNewDataNotification</a> method to notify SerCx2 when the driver detects that one or more bytes of received data either are ready to be transferred or have already been transferred by the system DMA controller.

The new-data notification enabled by the <i>EvtSerCx2SystemDmaReceiveEnableNewDataNotification</i> function is a one-shot notification. After this function is called and the serial controller driver sends a new-data notification to SerCx2, no further notification is sent until SerCx2 calls the function again to enable another notification.

The <i>EvtSerCx2SystemDmaReceiveEnableNewDataNotification</i> function typically enables an interrupt to be triggered when the serial controller receives data from the peripheral device.

No more than one new-data notification can be pending at a time. After SerCx2 calls the <i>EvtSerCx2SystemDmaReceiveEnableNewDataNotification</i> function to enable a new-data notification, SerCx2 does not call this function again until the controller driver calls <b>SerCx2SystemDmaReceiveNewDataNotification</b>.

A pending new-data notification can be canceled if the associated read request times out or is canceled. To cancel a new-data notification for a system-DMA-receive transaction, SerCx2 calls the <a href="..\sercx\nc-sercx-evt_sercx2_system_dma_receive_cancel_new_data_notification.md">EvtSerCx2SystemDmaReceiveCancelNewDataNotification</a> event callback function. A driver that implements an <i>EvtSerCx2SystemDmaReceiveEnableNewDataNotification</i> function must also implement an <i>EvtSerCx2SystemDmaReceiveCancelNewDataNotification</i> function.

SerCx2 uses new-data notifications to efficiently manage interval time-outs that occur during the handling of read requests that are processed as system-DMA-receive transactions.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn265343">SerCx2 System-DMA-Receive Transactions</a>.



## -see-also

<a href="..\sercx\nc-sercx-evt_sercx2_system_dma_receive_cancel_new_data_notification.md">EvtSerCx2SystemDmaReceiveCancelNewDataNotification</a>

<a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMARECEIVE</a>

<a href="..\sercx\nf-sercx-sercx2systemdmareceivecreate.md">SerCx2SystemDmaReceiveCreate</a>

<a href="..\sercx\nf-sercx-sercx2systemdmareceivenewdatanotification.md">SerCx2SystemDmaReceiveNewDataNotification</a>

<a href="..\sercx\nc-sercx-evt_sercx2_system_dma_receive_cleanup_transaction.md">EvtSerCx2SystemDmaReceiveCleanupTransaction</a>

<a href="..\wdm\nc-wdm-pread_dma_counter.md">ReadDmaCounter</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20EVT_SERCX2_SYSTEM_DMA_RECEIVE_ENABLE_NEW_DATA_NOTIFICATION callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

