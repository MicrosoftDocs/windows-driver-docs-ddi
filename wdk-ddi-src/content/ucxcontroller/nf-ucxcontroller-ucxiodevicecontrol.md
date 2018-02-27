---
UID: NF:ucxcontroller.UcxIoDeviceControl
title: UcxIoDeviceControl function
author: windows-driver-content
description: Allows USB host controller extension (UCX) to handle an I/O control code (IOCTL) request from user mode.
old-location: buses\_ucxiodevicecontrol.htm
old-project: usbref
ms.assetid: 7C1DD018-2EDF-48BB-8DFC-ADAF72A1909D
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UcxIoDeviceControl, UcxIoDeviceControl method [Buses], buses._ucxiodevicecontrol, ucxcontroller/UcxIoDeviceControl
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ucxcontroller.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Ucxcontroller.h
api_name:
-	UcxIoDeviceControl
product: Windows
targetos: Windows
req.typenames: UCX_CONTROLLER_STATE
req.product: Windows 10 or later.
---

# UcxIoDeviceControl function


## -description


    Allows USB host controller extension (UCX) to handle an  I/O control code (IOCTL) request from user mode.  


## -syntax


````
BOOL UcxIoDeviceControl(
  [in] WDFDEVICE  Device,
  [in] WDFREQUEST Request,
  [in] size_t     OutputBufferLength,
  [in] size_t     InputBufferLength,
  [in] ULONG      IoControlCode
);
````


## -parameters




### -param Device [in]

A handle to the framework device object that the client driver retrieved in the previous call to <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>.


### -param Request [in]

A handle to a framework request object that represents the user-mode IOCTL request. 


### -param OutputBufferLength [in]

The length, in bytes, of the request's output buffer, if an output buffer 
        is available.


### -param InputBufferLength [in]

The length, in bytes, of the request's input buffer, if an input buffer 
        is available.


### -param IoControlCode [in]

The driver-defined or system-defined IOCTL that is 
        associated with the request.


## -returns



If the operation is successful, the method returns TRUE. Otherwise it returns FALSE.




## -remarks



The client driver can call this method to allow UCX to handle IOCTLs listed in this table: <a href="https://docs.microsoft.com/en-us/windows/iot-core/learn-about-hardware/hardwarecompatlist">User-Mode IOCTLs for USB</a>. If the IOCTL code is <a href="..\usbioctl\ni-usbioctl-ioctl_usb_diagnostic_mode_off.md">IOCTL_USB_DIAGNOSTIC_MODE_OFF</a> or <a href="..\usbioctl\ni-usbioctl-ioctl_usb_diagnostic_mode_on.md">IOCTL_USB_DIAGNOSTIC_MODE_ON</a>, UCX completes the request successfully. For IOCTLS that are used to retrieve the USB host controllers
    driver key name, such as <a href="..\usbioctl\ni-usbioctl-ioctl_usb_get_root_hub_name.md">IOCTL_USB_GET_ROOT_HUB_NAME</a> or <a href="..\usbioctl\ni-usbioctl-ioctl_get_hcd_driverkey_name.md">IOCTL_GET_HCD_DRIVERKEY_NAME</a>, UCX retrieves the Unicode string. If the user mode IOCTL is <a href="https://msdn.microsoft.com/library/windows/hardware/ff537344">IOCTL_USB_USER_REQUEST</a>, the input and output buffer lengths must be equal and the output buffer must contain the <a href="https://msdn.microsoft.com/library/windows/hardware/ff539187">USBUSER_REQUEST_HEADER</a> structure. For the remaining IOCTLs, UCX  returns FALSE and the client driver can provide its own handling logic.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
Controller_WdfEvtIoDeviceControl(
    WDFQUEUE    WdfQueue,
    WDFREQUEST  WdfRequest,
    size_t      OutputBufferLength,
    size_t      InputBufferLength,
    ULONG       IoControlCode
)
/*++

Routine Description:

    This routine is a callback function which is called by WDF when a driver
    receives an I/O control request from the queue this callback is registered
    with.

    The controller driver calls UcxIoDeviceControl() to allow UCX to try and
    handle the IOCTL.  If UCX cannot handle the IOCTL, the controller driver
    must handle it, perhaps by failing it.

    The default queue only expects to receive IOCTLs from user mode (via the
    interface defined by GUID_DEVINTERFACE_USB_HOST_CONTROLLER).

Arguments:

    WdfQueue - A handle to the framework I/O queue object.

    WdfRequest - A handle to the framework request object that contains the IOCTL.

    OutputBufferLength - Length of the IOCTL output buffer, if an output buffer
        is available.

    InputBufferLength - Length of the IOCTL input buffer, if an input buffer
        is available.

    IoControlCode - I/O control code associated with the request.

Return Value:

    None.

--*/
{
    KPROCESSOR_MODE requestorMode;

    //
    // Allow UCX to try and handle the request
    //
    if (UcxIoDeviceControl(WdfIoQueueGetDevice(WdfQueue),
                           WdfRequest,
                           OutputBufferLength,
                           InputBufferLength,
                           IoControlCode)) {
        DbgTrace(TL_VERBOSE, Controller, "IoControlCode 0x%x was handled by UCX", IoControlCode);
        goto WdfEvtIoDeviceControlEnd;
    }

    //
    // Check that the request is coming from user mode
    //
    requestorMode = WdfRequestGetRequestorMode(WdfRequest);

    if (requestorMode != UserMode) {
        DbgTrace(TL_WARNING, Controller, "Invalid RequestorMode %d", requestorMode);
    }

    //
    // UCX could not handle the request, so handle it here
    //
    switch (IoControlCode) {

    default:
        DbgTrace(TL_WARNING, Controller, "Unsupported IoControlCode 0x%x", IoControlCode);
        WdfRequestComplete(WdfRequest, STATUS_INVALID_DEVICE_REQUEST);
    }

WdfEvtIoDeviceControlEnd:

    return;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="https://docs.microsoft.com/en-us/windows/iot-core/learn-about-hardware/hardwarecompatlist">User-Mode IOCTLs for USB</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UcxIoDeviceControl method%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

