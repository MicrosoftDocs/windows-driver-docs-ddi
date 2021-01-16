---
UID: NC:sercx.EVT_SERCX_FILEOPEN
title: EVT_SERCX_FILEOPEN (sercx.h)
description: The EvtSerCxFileOpen event callback function notifies the serial controller driver that a client opened a file handle on the serial controller device and that a file object has been created to represent the device.
old-location: serports\evtsercxfileopen.htm
tech.root: serports
ms.date: 04/23/2018
keywords: ["EVT_SERCX_FILEOPEN callback function"]
ms.keywords: 1/EvtSerCxFileOpen, EVT_SERCX_FILEOPEN, EVT_SERCX_FILEOPEN callback, EvtSerCxFileOpen, EvtSerCxFileOpen callback function [Serial Ports], serports.evtsercxfileopen
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
 - EVT_SERCX_FILEOPEN
 - sercx/EVT_SERCX_FILEOPEN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - 1.0\Sercx.h
api_name:
 - EVT_SERCX_FILEOPEN
---

# EVT_SERCX_FILEOPEN callback function


## -description

The <i>EvtSerCxFileOpen</i> event callback function notifies the serial controller driver that a client opened a file handle on the serial controller device and that a file object has been created to represent the device.

## -parameters

### -param Device 

[in]
A WDFDEVICE handle to the framework device object that represents the serial controller.

## -returns

The <i>EvtSerCxFileOpen</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error status code.

## -remarks

The serial framework extension (SerCx) calls this function to prepare the serial controller hardware to accept requests for I/O operations. This function should configure the controller in a state in which it is ready to receive and transmit data. If interrupts are required, this function should enable interrupts. In addition, this function should allocate any memory that is required only during the lifetime of the file object. For example, this function can allocate an interrupt data buffer.

To register an <i>EvtSerCxFileOpen</i> callback function, the driver must call the <a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercxinitialize">SerCxInitialize</a> method.

For more information, see <a href="/windows-hardware/drivers/wdf/framework-file-objects">Framework File Objects</a>.


#### Examples

The function type for this callback is declared in Sercx.h, as follows.


```cpp
typedef NTSTATUS
  EVT_SERCX_FILEOPEN(
    __in WDFDEVICE Device
    );
```

To define an <i>EvtSerCxFileOpen</i> callback function that is named <code>MyEvtSerCxFileOpen</code>, you must first provide a function declaration that <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV) and other verification tools require, as follows.


```cpp
EVT_SERCX_FILEOPEN MyEvtSerCxFileOpen;
```

Then, implement your callback function as follows.


```cpp
NTSTATUS
  MyEvtSerCxFileOpen(
    __in WDFDEVICE Device
    )
{ ... }
```

For more information about SDV requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions Using Function Role Types for KMDF Drivers</a>.

<div class="code"></div>

## -see-also

<a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercxinitialize">SerCxInitialize</a>

