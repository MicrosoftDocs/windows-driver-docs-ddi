---
UID: NC:sercx.EVT_SERCX2_PIO_TRANSMIT_CANCEL_READY_NOTIFICATION
title: EVT_SERCX2_PIO_TRANSMIT_CANCEL_READY_NOTIFICATION
author: windows-driver-content
description: The EvtSerCx2PioTransmitCancelReadyNotification event callback function is called by version 2 of the serial framework extension (SerCx2) to cancel a ready notification that SerCx2 enabled in a previous call to the EvtSerCx2PioTransmitEnableReadyNotification event callback function.
old-location: serports\evtsercx2piotransmitcancelreadynotification.htm
old-project: serports
ms.assetid: 2483F6A6-67FE-4C75-9872-53F66B4BD658
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: serports.evtsercx2piotransmitcancelreadynotification, EvtSerCx2PioTransmitCancelReadyNotification callback function [Serial Ports], EvtSerCx2PioTransmitCancelReadyNotification, EVT_SERCX2_PIO_TRANSMIT_CANCEL_READY_NOTIFICATION, EVT_SERCX2_PIO_TRANSMIT_CANCEL_READY_NOTIFICATION, 2/EvtSerCx2PioTransmitCancelReadyNotification
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
-	EvtSerCx2PioTransmitCancelReadyNotification
product: Windows
targetos: Windows
req.typenames: SENSOR_VALUE_PAIR, *PSENSOR_VALUE_PAIR
req.product: Windows 10 or later.
---

# EVT_SERCX2_PIO_TRANSMIT_CANCEL_READY_NOTIFICATION callback


## -description


The <i>EvtSerCx2PioTransmitCancelReadyNotification</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to cancel a ready notification that SerCx2 enabled in a previous call to the <a href="..\sercx\nc-sercx-evt_sercx2_pio_transmit_enable_ready_notification.md">EvtSerCx2PioTransmitEnableReadyNotification</a> event callback function.


## -prototype


````
EVT_SERCX2_PIO_TRANSMIT_CANCEL_READY_NOTIFICATION EvtSerCx2PioTransmitCancelReadyNotification;

BOOLEAN EvtSerCx2PioTransmitCancelReadyNotification(
  _In_ SERCX2PIOTRANSMIT PioTransmit
)
{ ... }
````


## -parameters




### -param PioTransmit [in]

A <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIOTRANSMIT</a> handle to a PIO-transmit object. The serial controller driver previously called the <a href="..\sercx\nf-sercx-sercx2piotransmitcreate.md">SerCx2PioTransmitCreate</a> method to create this object.


## -returns


The <i>EvtSerCx2PioTransmitCancelReadyNotification</i> function returns <b>TRUE</b> if the ready notification was successfully disabled and the serial controller driver can guarantee that this notification will not cause the <a href="..\sercx\nf-sercx-sercx2piotransmitready.md">SerCx2PioTransmitReady</a> method to be called. 

The function returns <b>FALSE</b> if the driver has already called <b>SerCx2PioTransmitReady</b>, or is about to call this method.



## -remarks


Your serial controller driver must implement this function. The driver registers the function in the <a href="..\sercx\nf-sercx-sercx2piotransmitcreate.md">SerCx2PioTransmitCreate</a> call that creates the PIO-transmit object.

If the associated write request times out or is canceled while a ready notification is enabled, SerCx2 calls the <i>EvtSerCx2PioTransmitCancelReadyNotification</i> function to cancel the pending notification. If this call returns <b>FALSE</b>, SerCx2 expects the serial controller driver to call <a href="..\sercx\nf-sercx-sercx2piotransmitready.md">SerCx2PioTransmitReady</a>; only after this call does SerCx2 call the <a href="..\sercx\nc-sercx-evt_sercx2_pio_transmit_cleanup_transaction.md">EvtSerCx2PioTransmitCleanupTransaction</a> event callback function, if it is implemented, and complete the request.

To cancel a previously enabled ready notification, the <i>EvtSerCx2PioTransmitCancelReadyNotification</i> function typically disables the interrupt in the serial controller that indicates that the transmit FIFO is ready to accept more data. SerCx2 enabled this interrupt in a previous call to the <a href="..\sercx\nc-sercx-evt_sercx2_pio_transmit_enable_ready_notification.md">EvtSerCx2PioTransmitEnableReadyNotification</a> function.

For more information, see <a href="https://msdn.microsoft.com/3BEF9A3D-1FEF-4626-B07F-1670359062AF">SerCx2 PIO-Transmit Transactions</a>.



## -see-also

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIOTRANSMIT</a>

<a href="..\sercx\nf-sercx-sercx2piotransmitcreate.md">SerCx2PioTransmitCreate</a>

<a href="..\sercx\nc-sercx-evt_sercx2_pio_transmit_enable_ready_notification.md">EvtSerCx2PioTransmitEnableReadyNotification</a>

<a href="..\sercx\nf-sercx-sercx2piotransmitready.md">SerCx2PioTransmitReady</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20EVT_SERCX2_PIO_TRANSMIT_CANCEL_READY_NOTIFICATION callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

