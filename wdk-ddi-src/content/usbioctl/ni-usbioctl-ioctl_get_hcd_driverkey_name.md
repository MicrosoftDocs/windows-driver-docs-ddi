---
UID: NI:usbioctl.IOCTL_GET_HCD_DRIVERKEY_NAME
title: IOCTL_GET_HCD_DRIVERKEY_NAME
author: windows-driver-content
description: The IOCTL_GET_HCD_DRIVERKEY_NAME I/O control request retrieves the driver key name in the registry for a USB host controller driver.
old-location: buses\ioctl_get_hcd_driverkey_name.htm
old-project: usbref
ms.assetid: 2435ef20-c75c-4b28-9824-8428b2ac6326
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _USB_HUB_TYPE, USB_HUB_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_GET_HCD_DRIVERKEY_NAME
req.alt-loc: Usbioctl.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.typenames: USB_HUB_TYPE
req.product: Windows 10 or later.
---

# IOCTL_GET_HCD_DRIVERKEY_NAME IOCTL



## -description

The <b>IOCTL_GET_HCD_DRIVERKEY_NAME</b> I/O control request retrieves the driver key name in the registry for a USB host controller driver.



The <b>IOCTL_GET_HCD_DRIVERKEY_NAME</b> I/O control request retrieves the driver key name in the registry for a USB host controller driver.

<b>IOCTL_GET_HCD_DRIVERKEY_NAME</b> is a user-mode I/O control request. This request targets the USB host controller (GUID_DEVINTERFACE_USB_HOST_CONTROLLER).



## -syntax

````

/*++

Routine Description:

This routine prints the name of the driver key associated with
the specified host controller driver.

Arguments:

HCD - Handle for host controller driver.

Return Value: Boolean that indicates success or failure.

--*/

BOOL GetHCDDriverKeyName (HANDLE  HCD)
{
    BOOL                    success;
    ULONG                   nBytes;
    USB_HCD_DRIVERKEY_NAME  driverKeyName;
    PUSB_HCD_DRIVERKEY_NAME driverKeyNameW;

    driverKeyNameW = NULL;

    // 1. Get the length of the name of the driver key.
    success = DeviceIoControl(HCD,
        IOCTL_GET_HCD_DRIVERKEY_NAME,
        NULL,
        0,
        &driverKeyName,
        sizeof(driverKeyName),
        &nBytes,
        NULL);

    if (!success) 
    {
        printf("First IOCTL_GET_HCD_DRIVERKEY_NAME request failed\n");
        goto GetHCDDriverKeyNameDone;
    }

    //2. Get the length of the driver key name.
    nBytes = driverKeyName.ActualLength;

    if (nBytes <= sizeof(driverKeyName)) 
    {
        printf("Incorrect length received by IOCTL_GET_HCD_DRIVERKEY_NAME.\n");
        goto GetHCDDriverKeyNameDone;
    }

    // 3. Allocate memory for a USB_HCD_DRIVERKEY_NAME
    //    to hold the driver key name.
    driverKeyNameW = (PUSB_HCD_DRIVERKEY_NAME) malloc(nBytes);

    if (driverKeyNameW == NULL) 
    {
        printf("Failed to allocate memory.\n");
        goto GetHCDDriverKeyNameDone;
    }

    // Get the name of the driver key of the device attached to
    // the specified port.
    success = DeviceIoControl(HCD,
        IOCTL_GET_HCD_DRIVERKEY_NAME,
        NULL,
        0,
        driverKeyNameW,
        nBytes,
        &nBytes,
        NULL);

    if (!success) 
    {
        printf("Second IOCTL_GET_HCD_DRIVERKEY_NAME request failed.\n");
        goto GetHCDDriverKeyNameDone;
    }

    // print the driver key name. 
    printf("Driver Key Name: %s.\n", driverKeyNameW->DriverKeyName);


GetHCDDriverKeyNameDone:

    // Cleanup.
    // Free the allocated memory for USB_HCD_DRIVERKEY_NAME.

    if (driverKeyNameW != NULL) 
    {
        free(driverKeyNameW);
        driverKeyNameW = NULL;
    }

    return success;
}


````


## -ioctlparameters

### -input-buffer
None.


### -input-buffer-length
None.


### -output-buffer
The <b>AssociatedIrp.SystemBuffer</b> member specifies the address of a caller-allocated buffer that contains a <a href="..\usbioctl\ns-usbioctl-_usb_hcd_driverkey_name.md">USB_HCD_DRIVERKEY_NAME</a> structure. On output, this structure holds the driver key name. For more information, see Remarks.


### -output-buffer-length
The size of this buffer is specified in the <b>Parameters.DeviceIoControl.OutputBufferLength</b> member. 


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The USB stack sets <b>Irp-&gt;IoStatus.Status</b> to STATUS_SUCCESS if the request is successful. Otherwise, the USB stack sets <b>Status</b> to the appropriate error condition, such as STATUS_INVALID_PARAMETER or STATUS_INSUFFICIENT_RESOURCES.


## -remarks
To get the driver key name in  the registry, you must perform the following tasks: 

The following example code shows how to send the <b>IOCTL_GET_HCD_DRIVERKEY_NAME</b> I/O control request.


## -see-also
<dl>
<dt>
<a href="..\usbioctl\ns-usbioctl-_usb_hcd_driverkey_name.md">USB_HCD_DRIVERKEY_NAME</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20IOCTL_GET_HCD_DRIVERKEY_NAME control code%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

