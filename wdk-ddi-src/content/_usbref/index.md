---
UID: TP:usbref
ms.assetid: 3ef75da3-dd0a-3f40-b741-d6c381f1ed78
ms.date: 05/09/2018
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
product:
- Windows
---

# Universal Serial Bus (USB)

## -description

This reference section describes the driver programming interfaces that are included in the [Windows Driver Kit (WDK)](https://docs.microsoft.com/windows-hardware/drivers/download-the-wdk). The programming interfaces are used for developing drivers that interact with USB devices, host controllers, connectors. These include export functions that the drivers can call, callback routines that the driver can implement, I/O requests that the driver can send to the Microsoft-provided USB driver stack, and various data structures that are used in those requests.

For the programming guide, see [Universal Serial Bus (USB)](https://docs.microsoft.com/windows-hardware/drivers/usbcon).

## Common USB client driver reference

A Windows Driver Model (WDM)-based USB client driver can call functions to communicate with the Microsoft-provided USB driver stack. These functions are defined in Usbdlib.h and the client driver requires the Usbdex.lib library. The library gets loaded and statically linked to the client driver module when it is built. A client driver that calls these routines can run on Windows Vista and later versions of Windows.

### Programming Guide
[Developing Windows client drivers for USB devices](https://docs.microsoft.com/windows-hardware/drivers/usbcon/usb-driver-development-guide).

### Headers
 * [usb.h](../usb/index.md)
 * [usbbusif.h](../usbbusif/index.md)
 * [usbdlib.h](../usbdlib/index.md)
 * [usbfnattach.h](../usbfnattach/index.md)
 * [usbfnbase.h](../usbfnbase/index.md)
 * [usbfnioctl.h](../usbfnioctl/index.md)
 * [usbioctl.h](../usbioctl/index.md)
 * [usbiodef.h](../usbiodef/index.md)
 * [usbspec.h](../usbspec/index.md)



## Deprecated functions, IOCTL requests for all USB drivers

These functions have been deprecated.

>Do not use.

- USBD_CalculateUsbBandwidth 
- USBD_CreateConfigurationRequest 
- USBD_Debug_LogEntry 
- USBD_GetUSBDIVersion 
- USBD_ParseConfigurationDescriptor 
- USBD_QueryBusTime 
- USBD_RegisterHcFilter 

These I/O requests have been deprecated or reserved for internal use. 

>USB client drivers must not use these I/O requests:

- IOCTL_USB_DIAG_IGNORE_HUBS_OFF 
- IOCTL_USB_DIAG_IGNORE_HUBS_ON 
- IOCTL_USB_DIAGNOSTIC_MODE_OFF 
- IOCTL_USB_DIAGNOSTIC_MODE_ON 
- IOCTL_USB_GET_HUB_CAPABILITIES 
- IOCTL_USB_HCD_DISABLE_PORT 
- IOCTL_USB_HCD_ENABLE_PORT 
- IOCTL_USB_HCD_GET_STATS_1 
- IOCTL_USB_HCD_GET_STATS_2 
- IOCTL_USB_RESET_HUB 


## Dual-role controller driver reference

A USB driver for a dual-role controller can behave as a host controller or a function controller depending on the hardware to which it is connected. These controllers are common on mobile devices and allow for connections to PCs, as well as USB peripherals like keyboards and mice. A mobile device can behave as a peripheral when it is connected to a PC, allowing you to transfer files between your PC and the mobile device. In that scenario, the controller on the device operates in the function role. Conversely, the controller can operate in the host role when connected to USB peripherals like storage drives, keyboard, mice. 

One of the main responsibilities of a driver for a dual-role controller is to switch between those two roles, tearing down the previous role's device node and loading the device node for the new role. When writing the driver, use the WDF class extension-client driver model. For more information about the WDF class extension-client driver model, see Ursdevice.h.

### Programming Guide

For information about enabling a Windows system for USB dual-role support, see [USB Dual Role Driver Stack Architecture](https://docs.microsoft.com/windows-hardware/drivers/usbcon/usb-dual-role-driver-stack-architecture).

### Headers
 * [urscx.h](../urscx/index.md)
 * [ursdevice.h](../ursdevice/index.md)
 * [ursfuncenum.h](../ursfuncenum/index.md)
 * [ursglobals.h](../ursglobals/index.md)
 * [urstypes.h](../urstypes/index.md)

## Emulated host controller driver reference
Windows drivers can present non-USB devices as emulated USB devices. By using the WDF class extension-client driver model, you can write a driver that translates USB-level constructs (reset, data transfers) to the actual underlying bus by using the hardware’s interface. The class extension and the client driver represent an emulated host controller with a root hub that is capable of presenting an attached device to the system as an USB device.

- USB device emulation class extension (UdeCx). This is an in-box driver included Windows 10. 
- The client driver is written by an IHV/OEM. This driver is referred to as the UDE client driver. 

The driver pair loads as the FDO in the host controller device stack. The UDE client driver communicates with Udecx by using a set of methods and event callback functions to handle device requests and notify the class extension about various events.

### Programming Guide
[Developing Windows drivers for emulated USB devices (UDE)](https://docs.microsoft.com/windows-hardware/drivers/usbcon/developing-windows-drivers-for-emulated-usb-host-controllers-and-devices).

### Headers
 * [udecxfuncenum.h](../udecxfuncenum/index.md)
 * [udecxtypes.h](../udecxtypes/index.md)
 * [udecxurb.h](../udecxurb/index.md)
 * [udecxusbdevice.h](../udecxusbdevice/index.md)
 * [udecxusbendpoint.h](../udecxusbendpoint/index.md)
 * [udecxwdfdevice.h](../udecxwdfdevice/index.md)

## Function class driver reference
A USB function class driver implements the functionality of a specific interface (or group of interfaces) on the USB device. The class driver handle requests issued by user mode services, or it can forwards requests to USB function class extension (UFX) and its function client driver. Certain class drivers are included in Windows, such as MTP and IpOverUsb. Windows also provides a generic kernel-mode class driver, Generic USBFN (GenericUSBFn.sys). If a particular interface or functionality is not provided by a system-supplied driver, you might need write a function class driver. The class driver may be implemented as a kernel-mode driver by using Windows Driver Frameworks (WDF). Alternatively, you may implement it as a user-mode service. In that case, your class driver must be paired with the system-supplied class driver, Generic USBFN. For example, the MTP class driver runs as a user-mode service that transferring files to and from the device. 

### Headers

* [usbfnbase.h](../usbfnbase/index.md)
* [usbfnioctl.h](../usbfnioctl/index.md)

## USB function controller client driver reference
The USB function client driver is responsible for implementing a function controller-specific operations. The client driver communicates with the USB function class extension (UFX) module to handle endpoint data transfers, USB device state changes (reset, suspend, resume), attach/detach detection, port/charger detection. The client driver is also responsible for handling power management, and PnP events.

### Programming Guide
[Write a USB function controller client driver](https://docs.microsoft.com/windows-hardware/drivers/usbcon/function-client-driver)


### Headers

* [ufxclient.h](../ufxclient/index.md)


## Filter driver for supporting USB chargers

Write a filter driver that supports detection of chargers, if the function controller uses the in-box Synopsys and ChipIdea drivers. If you are writing a client driver for a proprietary function controller, charger/attach detection is integrated in the client driver by implementing [EVT_UFX_DEVICE_PROPRIETARY_CHARGER_SET_PROPERTY](../ufxclient/nc-ufxclient-evt_ufx_device_proprietary_charger_set_property.md), [EVT_UFX_DEVICE_PROPRIETARY_CHARGER_RESET](../ufxclient/nc-ufxclient-evt_ufx_device_proprietary_charger_reset.md), and [EVT_UFX_DEVICE_DETECT_PROPRIETARY_CHARGER](../ufxclient/nc-ufxclient-evt_ufx_device_proprietary_charger_detect.md).
### Programming Guide
[USB filter driver for supporting USB chargers](https://docs.microsoft.com/windows-hardware/drivers/usbcon/usb-filter-driver-for-supporting-chargers)

### Headers
* [usbfnattach.h](../usbfnattach/index.md)
* [ufxbase.h](../ufxbase/index.md)
* [ufxproprietarycharger.h](../ufxproprietarycharger/index.md)

## Host controller driver reference

The USB host controller extension is a system-supplied extension to the Kernel-Mode Driver Framework (KMDF). Within the Microsoft USB Driver Stack Architecture, UCX provides functionality to assist a host controller client driver in managing a USB host controller device. The client driver handles hardware operations and events, power management, and PnP events. UCX serves as an abstracted interface to the rest of the Microsoft USB 3.0 stack, queues requests to the client driver, and performs other tasks.

If you are developing an xHCI host controller that is not compliant with the specification or developing a custom non-xHCI hardware (such as a virtual host controller), you can write a host controller driver that communicates with the UCX class extension. 

### Programming Guide

[Developing Windows drivers for USB host controllers](https://docs.microsoft.com/windows-hardware/drivers/usbcon/developing-windows-drivers-for-usb-host-controllers)

### Headers

 * [ucxclass.h](../ucxclass/index.md)
 * [ucxcontroller.h](../ucxcontroller/index.md)
 * [ucxendpoint.h](../ucxendpoint/index.md)
 * [ucxfuncenum.h](../ucxfuncenum/index.md)
 * [ucxglobals.h](../ucxglobals/index.md)
 * [ucxroothub.h](../ucxroothub/index.md)
 * [ucxsstreams.h](../ucxsstreams/index.md)
 * [ucxusbdevice.h](../ucxusbdevice/index.md)


## Type-C driver reference
Windows 10 introduces support for the new USB connector: USB Type-C. You can write a driver for these scenarios:


|Scenario|Headers|Programming Guide|
|---|---|---|
|**If your USB Type-C hardware has the capability of handling the power delivery (PD) state machine.**|<p>[ucmcx.h](../ucmcx/index.md)</p><p>[ucmfuncenum.h](../ucmfuncenum/index.md)</p><p>[ucmglobals.h](../ucmglobals/index.md)</p><p>[ucmmanager.h](../ucmmanager/index.md)</p>|[Write a USB Type-C connector driver](https://docs.microsoft.com/windows-hardware/drivers/usbcon/bring-up-a-usb-type-c-connector-on-a-windows-system)|
|**If your driver wants to participate in the policy decisions for USB Type-C connectors.**|[Usbpmapi.h](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbpmapi/)|[Write a USB Type-C Policy Manager client driver](https://docs.microsoft.com/windows-hardware/drivers/usbcon/policy-manager-client)|
|**If your hardware does not support PD.**| <p>[ucmtcpcicx.h](../ucmtcpcicx/index.md)</p> <p>[ucmtcpcidevice.h](../ucmtcpcidevice/index.md)</p> <p>[ucmtcpcifuncenum.h](../ucmtcpcifuncenum/index.md)</p> <p>[ucmtcpciglobals.h](../ucmtcpciglobals/index.md)</p> <p>[ucmtcpciportcontroller.h](../ucmtcpciportcontroller/index.md)</p> <p>[ucmtcpciportcontrollerrequests.h](../ucmtcpciportcontrollerrequests/index.md)</p> <p>[ucmtcpcispec.h](../ucmtcpcispec/index.md)</p> <p>[ucmtypes.h](../ucmtypes/index.md)</p>|[Write a USB Type-C port controller driver](https://docs.microsoft.com/windows-hardware/drivers/usbcon/write-a-usb-type-c-port-controller-driver).
**If your embedded controller is connected over non-ACPI transport**|</p>[Ucmucsicx.h](../ucmucsicx/index.md)</p></p>[Ucmucsidevice.h](../ucmucsidevice/index.md)</p></p>[Ucmucsifuncenum.h](../ucmucsifuncenum/index.md)</p></p>[Ucmucsiglobals.h](../ucmucsiglobals/index.md)</p></p>[Ucmucsippm.h](../ucmucsippm/index.md)</p></p>[Ucmucsippmrequests.h](../ucmucsippmrequests/index.md)</p></p>[Ucmucsispec.h](../ucmucsispec/index.md)</p>|[Write a UCSI client driver](https://docs.microsoft.com/windows-hardware/drivers/usbcon/write-a-ucsi-driver)|