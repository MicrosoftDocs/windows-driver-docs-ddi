---
UID: NC:sercx.EVT_SERCX2_CONTROL
title: EVT_SERCX2_CONTROL (sercx.h)
description: The EvtSerCx2Control event callback function is called by version 2 of the serial framework extension (SerCx2) to handle a serial I/O control request.
old-location: serports\evtsercx2control.htm
tech.root: serports
ms.assetid: C7032B34-5912-48B1-8D59-BAE6C0FEFB2C
ms.date: 04/23/2018
keywords: ["EVT_SERCX2_CONTROL callback function"]
ms.keywords: 2/EvtSerCx2Control, EVT_SERCX2_CONTROL, EVT_SERCX2_CONTROL callback, EvtSerCx2Control, EvtSerCx2Control callback function [Serial Ports], serports.evtsercx2control
f1_keywords:
 - "sercx/EvtSerCx2Control"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- 2.0\Sercx.h
api_name:
- EvtSerCx2Control
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_SERCX2_CONTROL callback function


## -description


The <i>EvtSerCx2Control</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to handle a serial I/O control request.


## -parameters




### -param Device [in]

A WDFDEVICE handle to the framework device object that represents the serial controller. The serial controller driver created this object in its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback function. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2initializedevice">SerCx2InitializeDevice</a>.


### -param Request [in]

A WDFREQUEST handle to the framework request object that represents the serial I/O control request.


### -param OutputBufferLength [in]

The length, in bytes, of the output buffer for the serial I/O control request specified by the <i>Request</i> parameter.


### -param InputBufferLength [in]

The length, in bytes, of the input buffer for the serial I/O control request specified by the <i>Request</i> parameter.


### -param IoControlCode [in]

Specifies the I/O control code (IOCTL) from the serial I/O control request specified by the <i>Request</i> parameter. The IOCTLs for serial I/O control requests are defined in the Ntddser.h header file. For more information, see Remarks.


## -returns



The <i>EvtSerCx2Control</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error status code.




## -remarks



Your serial controller driver must implement this function. The driver registers the function in the call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2initializedevice">SerCx2InitializeDevice</a> method that finishes the initialization of the framework device object for the serial controller.

The <i>EvtSerCx2Control</i> function lets your driver handle certain serial I/O control requests that SerCx2 cannot handle. SerCx2 handles all processing for a subset of the serial IOCTLs that are defined in the Ntddser.h header file. However, SerCx2 relies on the driver to handle serial I/O control requests to perform hardware-dependent operations.

When SerCx2 receives a serial I/O control request that can be handled only by the serial controller driver, SerCx2 calls the <i>EvtSerCx2Control</i> function to hand off the I/O control request to the driver. The driver is responsible for completing this request. A driver that does not implement support for a particular I/O control request should complete this I/O control request with the STATUS_NOT_SUPPORTED error status code.

To complete the I/O control request, the driver typically calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcomplete">WdfRequestComplete</a> method and supplies, as input parameters, the <i>Request</i> parameter value and a status value to indicate whether the request was successful. This status value is written to the status block of the request.

The <i>EvtSerCx2Control</i> function's return value should always match the status value that this function writes to the status block of the I/O control request. The current implementation of SerCx2 ignores this return value.

SerCx2 calls the <i>EvtSerCx2Control</i> function to handle the IOCTLs shown in the following table. The column on the right side of the table indicates whether the <i>EvtSerCx2Control</i> function is required to implement support for a particular IOCTL.

<table>
<tr>
<th>I/O control request name</th>
<th>Required or optional</th>
</tr>
<tr>
<td>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_clr_dtr">IOCTL_SERIAL_CLR_DTR</a>
</td>
<td>
Optional

</td>
</tr>
<tr>
<td>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_clr_rts">IOCTL_SERIAL_CLR_RTS</a>
</td>
<td>
Required

</td>
</tr>
<tr>
<td>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_get_baud_rate">IOCTL_SERIAL_GET_BAUD_RATE</a>
</td>
<td>
Required

</td>
</tr>
<tr>
<td>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_get_commstatus">IOCTL_SERIAL_GET_COMMSTATUS</a>
</td>
<td>
Required

</td>
</tr>
<tr>
<td>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_get_dtrrts">IOCTL_SERIAL_GET_DTRRTS</a>
</td>
<td>
Required

</td>
</tr>
<tr>
<td>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_get_handflow">IOCTL_SERIAL_GET_HANDFLOW</a>
</td>
<td>
Required

</td>
</tr>
<tr>
<td>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_get_line_control">IOCTL_SERIAL_GET_LINE_CONTROL</a>
</td>
<td>
Required

</td>
</tr>
<tr>
<td>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_get_modem_control">IOCTL_SERIAL_GET_MODEM_CONTROL</a>
</td>
<td>
Required

</td>
</tr>
<tr>
<td>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_get_modemstatus">IOCTL_SERIAL_GET_MODEMSTATUS</a>
</td>
<td>
Required

</td>
</tr>
<tr>
<td>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_get_properties">IOCTL_SERIAL_GET_PROPERTIES</a>
</td>
<td>
Required

</td>
</tr>
<tr>
<td>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_baud_rate">IOCTL_SERIAL_SET_BAUD_RATE</a>
</td>
<td>
Required

</td>
</tr>
<tr>
<td>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_break_off">IOCTL_SERIAL_SET_BREAK_OFF</a>
</td>
<td>
Required

</td>
</tr>
<tr>
<td>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_break_on">IOCTL_SERIAL_SET_BREAK_ON</a>
</td>
<td>
Required

</td>
</tr>
<tr>
<td>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_dtr">IOCTL_SERIAL_SET_DTR</a>
</td>
<td>
Optional

</td>
</tr>
<tr>
<td>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_fifo_control">IOCTL_SERIAL_SET_FIFO_CONTROL</a>
</td>
<td>
Optional

</td>
</tr>
<tr>
<td>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_handflow">IOCTL_SERIAL_SET_HANDFLOW</a>
</td>
<td>
Required

</td>
</tr>
<tr>
<td>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_line_control">IOCTL_SERIAL_SET_LINE_CONTROL</a>
</td>
<td>
Required

</td>
</tr>
<tr>
<td>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_modem_control">IOCTL_SERIAL_SET_MODEM_CONTROL</a>
</td>
<td>
Required

</td>
</tr>
<tr>
<td>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_rts">IOCTL_SERIAL_SET_RTS</a>
</td>
<td>
Required

</td>
</tr>
</table>
 

The preceding table lists all of the serial IOCTLs that SerCx2 presents to the <i>EvtSerCx2Control</i> function. For any IOCTL not in this list, SerCx2 either handles the IOCTL, or immediately fails the IOCTL and sets the request status to STATUS_NOT_SUPPORTED. SerCx2 handles <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_apply_default_configuration">IOCTL_SERIAL_APPLY_DEFAULT_CONFIGURATION</a> requests, but calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_apply_config">EvtSerCx2ApplyConfig</a> event callback function during the processing of such a request. SerCx2 handles <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_purge">IOCTL_SERIAL_PURGE</a> requests, but might call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_purge_fifos">EvtSerCx2PurgeFifos</a> event callback function during the processing of such a request. SerCx does preliminary processing of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_wait_mask">IOCTL_SERIAL_SET_WAIT_MASK</a> requests, but calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_set_wait_mask">EvtSerCx2SetWaitMask</a> event callback function, if it is implemented, to finish handling such a request. For more information about SerCx2 support for serial IOCTLs, see <a href="https://docs.microsoft.com/previous-versions/dn265347(v=vs.85)">Serial I/O Request Interface</a>.


#### IOCTL_SERIAL_CLR_DTR and IOCTL_SERIAL_SET_DTR

If the <i>EvtSerCx2Control</i> function in your serial controller driver supports the <b>IOCTL_SERIAL_SET_DTR</b> request, this function should also support the <b>IOCTL_SERIAL_CLR_DTR</b> request, and vice versa. If your  driver does not support these two requests, the driver's handler for the <b>IOCTL_SERIAL_GET_DTRRTS</b> request should set the SERIAL_DTR_STATE flag bit in the output value for this request to zero.


#### IOCTL_SERIAL_GET_DTRRTS

The <i>EvtSerCx2Control</i> function in your serial controller driver must support the <b>IOCTL_SERIAL_GET_DTRRTS</b> request, but the driver's handler for this request is required to support only the SERIAL_RTS_STATE flag bit in the output value for this request. As an option, the driver can additionally support the SERIAL_DTR_STATE  flag bit. If the SERIAL_DTR_STATE  flag bit is not supported, set this bit to zero.


#### IOCTL_SERIAL_GET_COMMSTATUS

The <i>EvtSerCx2Control</i> function in your serial controller driver must support the <b>IOCTL_SERIAL_GET_COMMSTATUS</b> request, but the driver's handler for this request is required to support only the following members of the  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ns-ntddser-_serial_status">SERIAL_STATUS</a> structure used by this request:

<ul>
<li><b>Errors</b></li>
<li><b>HoldReasons</b></li>
</ul>
As an option, the driver can additionally support any of the other members of this structure. Set all unsupported members to zero.


#### IOCTL_SERIAL_GET_PROPERTIES

The <i>EvtSerCx2Control</i> function in your serial controller driver must support the <b>IOCTL_SERIAL_GET_PROPERTIES</b> request. The driver's handler for this request should set the <b>MaxBaud</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ns-ntddser-_serial_commprop">SERIAL_COMMPROP</a> structure used by this request to the maximum supported baud rate, expressed in bits per second (bps). For example, if the serial controller supports a maximum baud rate of 115,200 bps, the driver sets <b>MaxBaud</b> = 115200.


#### IOCTL_SERIAL_GET_MODEMSTATUS

The <i>EvtSerCx2Control</i> function in your serial controller driver must support the <b>IOCTL_SERIAL_GET_MODEMSTATUS</b> request. The driver's handler for this request should set the request's output value to the raw modem status register value read from the serial controller hardware.


#### IOCTL_SERIAL_GET_HANDFLOW and IOCTL_SERIAL_SET_HANDFLOW

The <i>EvtSerCx2Control</i> function in your serial controller driver must support the <b>IOCTL_SERIAL_GET_HANDFLOW</b> and <b>IOCTL_SERIAL_SET_HANDFLOW</b> requests, but is required to support only a subset of the flag bits that are defined for these requests. Flag bits are defined for the <b>ControlHandShake</b> and <b>FlowReplace</b> members of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ns-ntddser-_serial_handflow">SERIAL_HANDFLOW</a> structure that is used by these requests.

Your driver must support the following flag bit in the <b>ControlHandshake</b> member:

<ul>
<li>SERIAL_CTS_HANDSHAKE</li>
</ul>
As an option, a driver can support any of the other flag bits that are defined for the <b>ControlHandshake</b> member.

Your driver must support the following flag bits in the <b>FlowReplace</b> member:

<ul>
<li>SERIAL_RTS_CONTROL</li>
<li>SERIAL_RTS_HANDSHAKE</li>
</ul>
As an option, a driver can support any of the other flag bits that are defined for the <b>FlowReplace</b> member. However, these other flag bits are rarely, if ever, needed, and Microsoft recommends against supporting them.

A driver that does not support a particular flag bit in the <b>ControlHandShake</b> or <b>FlowReplace</b> member should set this flag bit to zero in the output value for the <b>IOCTL_SERIAL_GET_HANDFLOW</b> request. If an <b>IOCTL_SERIAL_SET_HANDFLOW</b> request specifies a <b>ControlHandshake</b> or <b>FlowReplace</b> flag bit that the driver does not support, the <i>EvtSerCx2Control</i> function should fail the request and return STATUS_INVALID_PARAMETER.

As an option, a driver can support the <b>XonLimit</b> and <b>XoffLimit</b> members of the <b>SERIAL_HANDFLOW</b> structure. However, these members are rarely, if ever, needed, and Microsoft recommends against supporting them. A driver that does not support the <b>XonLimit</b> and <b>XoffLimit</b> members should set these members to zero in the output value for the <b>IOCTL_SERIAL_GET_HANDFLOW</b> request. If an <b>IOCTL_SERIAL_SET_HANDFLOW</b> request specifies a nonzero <b>XonLimit</b> or <b>XoffLimit</b> member and the driver does not support these members, the <i>EvtSerCx2Control</i> function should fail the request and return STATUS_NOT_IMPLEMENTED.


#### Examples

To define an <i>EvtSerCx2Control</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtSerCx2Control</i> callback function that is named <code>MyControl</code>, use the <b>EVT_SERCX2_CONTROL</b> function type, as shown in this code example:

<div class="code"><span codelanguage="cpp"><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_SERCX2_CONTROL  MyControl;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows:

<div class="code"><span codelanguage="cpp"><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
NTSTATUS
  MyControl(
    WDFDEVICE  Device,
    WDFREQUEST  Request,
    size_t  OutputBufferLength,
    size_t  InputBufferLength,
    ULONG  IoControlCode
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_SERCX2_CONTROL</b> function type is defined in the Sercx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_SERCX2_CONTROL</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_apply_config">EvtSerCx2ApplyConfig</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_purge_fifos">EvtSerCx2PurgeFifos</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nc-sercx-evt_sercx2_set_wait_mask">EvtSerCx2SetWaitMask</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ns-ntddser-_serial_commprop">SERIAL_COMMPROP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/serports/peripheral-drivers-for-devices-on-sercx2-managed-serial-ports">SERIAL_EV_XXX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ns-ntddser-_serial_handflow">SERIAL_HANDFLOW</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ns-ntddser-_serial_status">SERIAL_STATUS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2initializedevice">SerCx2InitializeDevice</a>
 

 

