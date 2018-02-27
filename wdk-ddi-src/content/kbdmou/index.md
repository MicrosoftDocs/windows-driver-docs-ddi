---
UID: NA:kbdmou
ms.assetid: 7916a78e-8897-372f-8e32-22081a9589d3
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Kbdmou.h header



This header is used by Human Interface Devices (HID). For more information, see
- [Human Interface Devices (HID)](../_hid/index.md)

This section includes the following topics about Kbdclass, the class driver for device class GUID_CLASS_KEYBOARD and the system class driver Mouclass. The Mouclass driver supports the device class GUID_CLASS_MOUSE, in Microsoft Windows 2000 and later operating systems:

## Keyboard class driver

Windows uses Kbdclass as the class driver for all keyboard devices that are installed in a system. The Windows Win32 subsystem opens all keyboard devices for its exclusive use. Applications cannot open the keyboard devices operated by Kbdclass.

Kbdclass can work in combination with an optional upper-level filter driver for a PS/2-style keyboard device. Kbfiltr, a sample upper-level keyboard filter driver in the MSDN Code Gallery, demonstrates how to customize the operation of a keyboard device.

Kbdclass changes these device control requests into internal device control request and sends the changed request down the device stack.


-   IOCTL_KEYBOARD_QUERY_ATTRIBUTES
-   IOCTL_KEYBOARD_QUERY_INDICATORS
-   IOCTL_KEYBOARD_QUERY_INDICATOR_TRANSLATION
-   IOCTL_KEYBOARD_QUERY_TYPEMATIC
-   IOCTL_KEYBOARD_SET_INDICATORS
-   IOCTL_KEYBOARD_SET_TYPEMATIC


Filter drivers between the class and function drivers can filter device control requests either before they send the request down the device stack or after the lower-level drivers complete the request.

If Kbdclass does not support the request, it completes the request with a status of STATUS_INVALID_DEVICE_REQUEST.

### Input and Output

The Parameters.DeviceIoControlCode.IoControlCode member specifies the control code.

The AssociatedIrp-&gt;SystemBuffer member is used for request-specific input and output.

The Parameters.DeviceIoControl.InputBufferLength member is used to input the request-specific size of the input buffer.

The Parameters.DeviceIoControl.OutputBufferLength member is used to input the request-specific size of the output buffer.

### I/O Status Block

Usually, the Information member is set to zero or to the number of bytes returned in the output buffer. Information can also return request-specific values or pointers.

The Status member is set to a request-specific value. Status is set to STATUS_INVALID_DEVICE_REQUEST if Kbdclass does not support the request.

The following control requests are not changed to internal device control requests. Kbdclass skips the current IRP stack location and sends these requests down the device stack to be completed by the lower-level drivers:

-   IOCTL_GET_SYS_BUTTON_CAPS
-   IOCTL_GET_SYS_BUTTON_EVENT
-   IOCTL_HID_GET_DRIVER_CONFIG
-   IOCTL_HID_SET_DRIVER_CONFIG
-   IOCTL_HID_GET_POLL_FREQUENCY_MSEC
-   IOCTL_HID_SET_POLL_FREQUENCY_MSEC
-   IOCTL_GET_NUM_DEVICE_INPUT_BUFFERS
-   IOCTL_SET_NUM_DEVICE_INPUT_BUFFERS
-   IOCTL_HID_GET_COLLECTION_INFORMATION
-   IOCTL_HID_GET_COLLECTION_DESCRIPTOR
-   IOCTL_HID_FLUSH_QUEUE
-   IOCTL_HID_SET_FEATURE
-   IOCTL_HID_GET_FEATURE
-   IOCTL_GET_PHYSICAL_DESCRIPTOR
-   IOCTL_HID_GET_HARDWARE_ID
-   IOCTL_HID_GET_MANUFACTURER_STRING
-   IOCTL_HID_GET_PRODUCT_STRING
-   IOCTL_HID_GET_SERIALNUMBER_STRING
-   IOCTL_HID_GET_INDEXED_STRING

 
## Mouse class driver

Windows uses Mouclass as the class driver for all mouse devices installed in a system. The Windows Win32 subsystem opens all mouse devices for its exclusive use. Applications cannot open the mouse devices opened by Mouclass.

Mouclass can work in combination with an optional upper-level mouse filter driver for a PS/2-style mouse device. Moufiltr, a sample upper-level mouse filter driver in the MSDN Code Gallery, can be used to customize the operation of a mouse device.

Mouclass changes an IOCTL_MOUSE_QUERY_ATTRIBUTES request into an internal device control request and sends the changed request down the device stack.

Mouclass also sends a number of other device control requests for Plug and Play devices down the device stack without changing the request to an internal device control request. For a list of these requests, see IOCTL_Xxx Device Control Requests.

Filter drivers between the class and function drivers can filter these requests before they send the request down the device stack or after the lower-level drivers complete the request.

If Mouclass does not support the request, it completes the request with a status of STATUS_INVALID_DEVICE_REQUEST.


Note   Mouclass supports legacy devices and Plug and Play devices. When appropriate, this material distinguishes between the operation of Mouclass for a legacy device and a Plug and Play device. If no distinction is made, the description applies to both legacy and Plug and Play devices.
 
Mouclass changes an IOCTL_MOUSE_QUERY_ATTRIBUTES request into an internal device control request and sends the changed request down the device stack.

Mouclass also sends a number of other device control requests for Plug and Play devices down the device stack without changing the request to an internal device control request. For a list of these requests, see IOCTL_Xxx Device Control Requests.

Filter drivers between the class and function drivers can filter these requests before they send the request down the device stack or after the lower-level drivers complete the request.

If Mouclass does not support the request, it completes the request with a status of STATUS_INVALID_DEVICE_REQUEST.

 

