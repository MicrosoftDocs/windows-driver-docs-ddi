---
UID: NC:sercx.EVT_SERCX_CONTROL
title: EVT_SERCX_CONTROL (sercx.h)
description: The EvtSerCxControl event callback function handles an I/O control request that has an I/O control code (IOCTL) that the serial framework extension (SerCx) supports.
old-location: serports\evtsercxcontrol.htm
tech.root: serports
ms.assetid: 2A88BA68-48A7-4C00-8031-CCC50A0C090D
ms.date: 04/23/2018
keywords: ["EVT_SERCX_CONTROL callback function"]
ms.keywords: 1/EvtSerCxControl, EVT_SERCX_CONTROL, EVT_SERCX_CONTROL callback, EvtSerCxControl, EvtSerCxControl callback function [Serial Ports], serports.evtsercxcontrol
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
 - EVT_SERCX_CONTROL
 - sercx/EVT_SERCX_CONTROL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - 1.0\Sercx.h
api_name:
 - EvtSerCxControl
---

# EVT_SERCX_CONTROL callback function


## -description

The <i>EvtSerCxControl</i> event callback function handles an I/O control request that has an I/O control code (IOCTL) that the serial framework extension (SerCx) supports.

## -parameters

### -param Device 

[in]
A WDFDEVICE handle to the framework device object that represents the serial controller.

### -param Request 

[in]
A WDFREQUEST handle to the framework request object that represents the I/O control request.

### -param OutputBufferLength 

[in]
Specifies the length, in bytes, of the output buffer for the I/O control request specified by the <i>Request</i> parameter.

### -param InputBufferLength 

[in]
Specifies the length, in bytes, of the input buffer for the I/O control request specified by the <i>Request</i> parameter.

### -param IoControlCode 

[in]
Specifies the IOCTL from the I/O control request specified by the <i>Request</i> parameter.

## -returns

The <i>EvtSerCxControl</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error status code. For more information, see the following Remarks section.

## -remarks

The serial controller driver is required to implement this callback function. SerCx calls this function to hand off an I/O control request to the controller driver for processing. Before this function returns, it must complete the request either by performing the requested operation or by returning an error status. A driver that does not implement support for a particular request should return the STATUS_NOT_IMPLEMENTED error status for this request.

Typically, the <i>EvtSerCxControl</i> function should synchronize to the controller driver's ISR before this function changes the settings in the hardware registers of the serial controller.

The <i>EvtSerCxControl</i> function's return value must match the status value that this function writes to the status block of the I/O control request. SerCx uses the return value to track the state of the controller driver and the serial controller hardware.

The following is a list of the IOCTLs that this callback function must be prepared to handle:

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_clear_stats">IOCTL_SERIAL_CLEAR_STATS</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_clr_dtr">IOCTL_SERIAL_CLR_DTR</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_clr_rts">IOCTL_SERIAL_CLR_RTS</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_get_baud_rate">IOCTL_SERIAL_GET_BAUD_RATE</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_get_chars">IOCTL_SERIAL_GET_CHARS</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_get_commstatus">IOCTL_SERIAL_GET_COMMSTATUS</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_get_dtrrts">IOCTL_SERIAL_GET_DTRRTS</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_get_handflow">IOCTL_SERIAL_GET_HANDFLOW</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_immediate_char">IOCTL_SERIAL_IMMEDIATE_CHAR</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_get_line_control">IOCTL_SERIAL_GET_LINE_CONTROL</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_get_modem_control">IOCTL_SERIAL_GET_MODEM_CONTROL</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_get_modemstatus">IOCTL_SERIAL_GET_MODEMSTATUS</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_get_properties">IOCTL_SERIAL_GET_PROPERTIES</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_get_stats">IOCTL_SERIAL_GET_STATS</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_lsrmst_insert">IOCTL_SERIAL_LSRMST_INSERT</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_baud_rate">IOCTL_SERIAL_SET_BAUD_RATE</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_break_off">IOCTL_SERIAL_SET_BREAK_OFF</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_break_on">IOCTL_SERIAL_SET_BREAK_ON</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_chars">IOCTL_SERIAL_SET_CHARS</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_dtr">IOCTL_SERIAL_SET_DTR</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_fifo_control">IOCTL_SERIAL_SET_FIFO_CONTROL</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_handflow">IOCTL_SERIAL_SET_HANDFLOW</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_line_control">IOCTL_SERIAL_SET_LINE_CONTROL</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_modem_control">IOCTL_SERIAL_SET_MODEM_CONTROL</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_rts">IOCTL_SERIAL_SET_RTS</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_xoff">IOCTL_SERIAL_SET_XOFF</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_xon">IOCTL_SERIAL_SET_XON</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_xoff_counter">IOCTL_SERIAL_XOFF_COUNTER</a>
To register an <i>EvtSerCxControl</i> callback function, the controller driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercxinitialize">SerCxInitialize</a> method during the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback.


#### Examples

The function type for this callback is declared in Sercx.h, as follows.

<div class="code"><span codelanguage="cpp"><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef NTSTATUS
  EVT_SERCX_CONTROL(
    __in WDFREQUEST Request,
    __in size_t OutputBufferLength,
    __in size_t InputBufferLength,
    __in ULONG IoControlCode
    );</pre>
</td>
</tr>
</table></span></div>
To define an <i>EvtSerCxControl</i> callback function that is named <code>MyEvtSerCxControl</code>, you must first provide a function declaration that <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV) and other verification tools require, as follows.

<div class="code"><span codelanguage="cpp"><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_SERCX_CONTROL MyEvtSerCxControl;</pre>
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
  MyEvtSerCxControl(
    __in WDFREQUEST Request,
    __in size_t OutputBufferLength,
    __in size_t InputBufferLength,
    __in ULONG IoControlCode
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

