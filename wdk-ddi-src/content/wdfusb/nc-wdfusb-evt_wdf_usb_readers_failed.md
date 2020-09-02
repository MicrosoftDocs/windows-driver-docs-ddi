---
UID: NC:wdfusb.EVT_WDF_USB_READERS_FAILED
title: EVT_WDF_USB_READERS_FAILED (wdfusb.h)
description: A driver's EvtUsbTargetPipeReadersFailed event callback function informs the driver that a continuous reader has reported an error while processing a read request.
old-location: wdf\evtusbtargetpipereadersfailed.htm
tech.root: wdf
ms.assetid: a9e21f47-1a60-419a-839e-8869f9fd4dd7
ms.date: 02/26/2018
keywords: ["EVT_WDF_USB_READERS_FAILED callback function"]
ms.keywords: DFUsbRef_ba1b1293-cdd5-481e-8dd1-3633eb9084b9.xml, EVT_WDF_USB_READERS_FAILED, EVT_WDF_USB_READERS_FAILED callback, EvtUsbTargetPipeReadersFailed, EvtUsbTargetPipeReadersFailed callback function, kmdf.evtusbtargetpipereadersfailed, wdf.evtusbtargetpipereadersfailed, wdfusb/EvtUsbTargetPipeReadersFailed
req.header: wdfusb.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_WDF_USB_READERS_FAILED
 - wdfusb/EVT_WDF_USB_READERS_FAILED
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - WdfUsb.h
api_name:
 - EvtUsbTargetPipeReadersFailed
---

# EVT_WDF_USB_READERS_FAILED callback function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtUsbTargetPipeReadersFailed</i> event callback function informs the driver that a continuous reader has reported an error while processing a read request.

## -parameters

### -param Pipe 

[in]
A handle to a framework pipe object.

### -param Status 

[in]
The <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS value</a> that the pipe's I/O target returned.

### -param UsbdStatus 

[in]
The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff539136(v=vs.85)">USBD_STATUS</a>-typed status value that the pipe's I/O target returned.

## -returns

The <i>EvtUsbTargetPipeReadersFailed</i> event callback function returns a Boolean value that, if <b>TRUE</b>, causes the framework to reset the USB pipe and then restart the continuous reader. If this function returns <b>FALSE</b>, the framework does not reset the device or restart the continuous reader.

## -remarks

To register an <i>EvtUsbTargetPipeReadersFailed</i> callback function, the driver must place the function's address in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_continuous_reader_config">WDF_USB_CONTINUOUS_READER_CONFIG</a> structure. For  information about when to add this function pointer, see the Remarks section of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdf_usb_continuous_reader_config_init">WDF_USB_CONTINUOUS_READER_CONFIG_INIT</a>.

If a driver has created a continuous reader for a USB pipe, the framework calls the driver's <i>EvtUsbTargetPipeReadersFailed</i> callback function if the driver's I/O target reports an error when it completes a read request. (If the I/O target successfully completes the request, the framework calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nc-wdfusb-evt_wdf_usb_reader_completion_routine">EvtUsbTargetPipeReadComplete</a> callback function.) 

Before the framework calls a driver's <i>EvtUsbTargetPipeReadersFailed</i> callback function, it tries to cancel all in-progress read requests. No read requests are in progress when the framework calls the <i>EvtUsbTargetPipeReadersFailed</i> callback function. The framework does not queue any additional read requests until the <i>EvtUsbTargetPipeReadersFailed</i> callback function returns.

For information about how the framework synchronizes calls to the <i>EvtUsbTargetPipeReadersFailed</i> callback function with calls to other callback functions, see the Remarks section of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nc-wdfusb-evt_wdf_usb_reader_completion_routine">EvtUsbTargetPipeReadComplete</a>.

The <i>EvtUsbTargetPipeReadersFailed</i> callback function must not call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetstop">WdfIoTargetStop</a> to stop the continuous reader's USB target. (In fact, calling <b>WdfIoTargetStop</b> in an <i>EvtUsbTargetPipeReadersFailed</i> callback function causes a deadlock.) In addition, the callback function must not call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetstart">WdfIoTargetStart</a> to restart the continuous reader. Instead, the framework restarts the reader if the callback function returns <b>TRUE</b>. For more information about when to call <b>WdfIoTargetStart</b> and <b>WdfIoTargetStop</b> for a continuous reader, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/working-with-usb-pipes">Working with USB Pipes</a>.

If a driver does not provide an <i>EvtUsbTargetPipeReadersFailed</i> callback function and the driver's I/O target reports an error, the framework resets the USB pipe and restarts the continuous reader. 

For more information about the <i>EvtUsbTargetPipeReadersFailed</i> callback function and USB I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/usb-i-o-targets">USB I/O Targets</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nc-wdfusb-evt_wdf_usb_reader_completion_routine">EvtUsbTargetPipeReadComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/ns-wdfusb-_wdf_usb_continuous_reader_config">WDF_USB_CONTINUOUS_READER_CONFIG</a>

