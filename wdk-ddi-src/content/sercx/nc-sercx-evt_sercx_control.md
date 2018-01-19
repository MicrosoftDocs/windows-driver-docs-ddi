---
UID: NC:sercx.EVT_SERCX_CONTROL
title: EVT_SERCX_CONTROL
author: windows-driver-content
description: The EvtSerCxControl event callback function handles an I/O control request that has an I/O control code (IOCTL) that the serial framework extension (SerCx) supports.
old-location: serports\evtsercxcontrol.htm
old-project: serports
ms.assetid: 2A88BA68-48A7-4C00-8031-CCC50A0C090D
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SENSOR_VALUE_PAIR, *PSENSOR_VALUE_PAIR, SENSOR_VALUE_PAIR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: sercx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: EvtSerCxControl
req.alt-loc: 1.0\Sercx.h
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
req.typenames: *PSENSOR_VALUE_PAIR, SENSOR_VALUE_PAIR
req.product: Windows 10 or later.
---

# EVT_SERCX_CONTROL callback



## -description
The <i>EvtSerCxControl</i> event callback function handles an I/O control request that has an I/O control code (IOCTL) that the serial framework extension (SerCx) supports.



## -prototype

````
EVT_SERCX_CONTROL EvtSerCxControl;

NTSTATUS EvtSerCxControl(
  _In_ WDFDEVICE  Device,
  _In_ WDFREQUEST Request,
  _In_ size_t     OutputBufferLength,
  _In_ size_t     InputBufferLength,
  _In_ ULONG      IoControlCode
)
{ ... }
````


## -parameters

### -param Device [in]

A WDFDEVICE handle to the framework device object that represents the serial controller.


### -param Request [in]

A WDFREQUEST handle to the framework request object that represents the I/O control request.


### -param OutputBufferLength [in]

Specifies the length, in bytes, of the output buffer for the I/O control request specified by the <i>Request</i> parameter.


### -param InputBufferLength [in]

Specifies the length, in bytes, of the input buffer for the I/O control request specified by the <i>Request</i> parameter.


### -param IoControlCode [in]

Specifies the IOCTL from the I/O control request specified by the <i>Request</i> parameter.


## -returns
The <i>EvtSerCxControl</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error status code. For more information, see the following Remarks section.


## -remarks
The serial controller driver is required to implement this callback function. SerCx calls this function to hand off an I/O control request to the controller driver for processing. Before this function returns, it must complete the request either by performing the requested operation or by returning an error status. A driver that does not implement support for a particular request should return the STATUS_NOT_IMPLEMENTED error status for this request.

Typically, the <i>EvtSerCxControl</i> function should synchronize to the controller driver's ISR before this function changes the settings in the hardware registers of the serial controller.

The <i>EvtSerCxControl</i> function's return value must match the status value that this function writes to the status block of the I/O control request. SerCx uses the return value to track the state of the controller driver and the serial controller hardware.

The following is a list of the IOCTLs that this callback function must be prepared to handle:

To register an <i>EvtSerCxControl</i> callback function, the controller driver calls the <a href="..\sercx\nf-sercx-sercxinitialize.md">SerCxInitialize</a> method during the <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback.

The function type for this callback is declared in Sercx.h, as follows.

To define an <i>EvtSerCxControl</i> callback function that is named <code>MyEvtSerCxControl</code>, you must first provide a function declaration that <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV) and other verification tools require, as follows.

Then, implement your callback function as follows.

For more information about SDV requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions Using Function Role Types for KMDF Drivers</a>.


## -see-also
<dl>
<dt>
<a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a>
</dt>
<dt>
<a href="..\sercx\nf-sercx-sercxinitialize.md">SerCxInitialize</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20EVT_SERCX_CONTROL callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

