---
UID: NC:sercx.EVT_SERCX_TRANSMIT
title: EVT_SERCX_TRANSMIT (sercx.h)
description: The EvtSerCxTransmit event callback function prepares the serial controller device (UART) to do a write (transmit) operation.
old-location: serports\evtsercxtransmit.htm
tech.root: serports
ms.assetid: B32335E4-3BDF-4161-9BE2-CF3557D76988
ms.date: 04/23/2018
keywords: ["EVT_SERCX_TRANSMIT callback function"]
ms.keywords: 1/EvtSerCxTransmit, EVT_SERCX_TRANSMIT, EVT_SERCX_TRANSMIT callback, EvtSerCxTransmit, EvtSerCxTransmit callback function [Serial Ports], serports.evtsercxtransmit
req.header: sercx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8.
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
req.irql: Called at IRQL <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_SERCX_TRANSMIT
 - sercx/EVT_SERCX_TRANSMIT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - 1.0\Sercx.h
api_name:
 - EvtSerCxTransmit
---

# EVT_SERCX_TRANSMIT callback function


## -description

The <i>EvtSerCxTransmit</i> event callback function prepares the serial controller device (UART) to do a write (transmit) operation.

## -parameters

### -param Device 

[in]
A WDFDEVICE handle to the framework device object that represents the serial controller.

### -param Length 

[in]
The number of bytes to be transmitted. The controller driver can use this value as a hint to decide whether to use PIO or DMA to perform the data transfer.

## -returns

The <i>EvtSerCxTransmit</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error status code.

## -remarks

The serial framework extension (SerCx) calls this function to configure the serial controller hardware to transmit data. If necessary, the <i>EvtSerCxTransmit</i> function can enable interrupts.

The <i>EvtSerCxTransmit</i> function does not necessarily write the output data to the transmit FIFO buffer. Depending on the serial controller hardware or the type of transfer, this function might set up a DMA operation to write the data, or it might schedule a transmit/receive DPC function to write the data. The serial controller driver implements this DPC function to transmit data to the serial controller and to receive data from the controller. During the DPC, the DPC function determines whether data is available to be transmitted and, if so, uses PIO to transfer the data to the transmit FIFO in the serial controller.

If the transmit FIFO in the serial controller is full or nearly full, but the FIFO's low-water-mark interrupt is enabled, the <i>EvtSerCxTransmit</i> function can simply return. Later, the controller driver's ISR can schedule the transmit/receive DPC function to run, and this function can transfer more output data to the transmit FIFO.

To register an <i>EvtSerCxTransmit</i> callback function, the controller driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercxinitialize">SerCxInitialize</a> method during the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback.


#### Examples

The function type for this callback is declared in Sercx.h, as follows.

<div class="code"><span codelanguage="cpp"><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef NTSTATUS
  EVT_SERCX_TRANSMIT(
    __in WDFDEVICE Device
    );</pre>
</td>
</tr>
</table></span></div>
To define an <i>EvtSerCxTransmit</i> callback function that is named <code>MyEvtSerCxTransmit</code>, you must first provide a function declaration that <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV) and other verification tools require, as follows.

<div class="code"><span codelanguage="cpp"><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_SERCX_TRANSMIT MyEvtSerCxTransmit;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows.

<div class="code"><span codelanguage="cpp"><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
  MyEvtSerCxTransmit(
    __in WDFDEVICE Device
    )
{ ... }</pre>
</td>
</tr>
</table></span></div>
For more information about SDV requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions Using Function Role Types for KMDF Drivers</a>.

<div class="code"></div>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercxinitialize">SerCxInitialize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdpc/nf-wdfdpc-wdfdpcenqueue">WdfDpcEnqueue</a>

