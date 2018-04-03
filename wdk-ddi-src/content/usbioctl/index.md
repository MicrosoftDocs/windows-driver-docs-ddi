---
UID: NA:usbioctl
ms.assetid: 0cb01349-16ee-3a58-babe-fd5b85e93d9f
ms.author: windowsdriverdev
ms.date: 04/03/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Usbioctl.h header


## -description


This header is used by usbref. For more information, see:

- [Universal Serial Bus (USB)](../_usbref/index.md)

This section contains reference topics for the Usbioctl.h header. This header contains programming interfaces that are exposed by the Microsoft-provided USB driver stack.


In this section


Topic
Description




HUB_DEVICE_CONFIG_INFO



The HUB_DEVICE_CONFIG_INFO structure is used in conjunction with the kernel-mode IOCTL, IOCTL_INTERNAL_USB_GET_DEVICE_CONFIG_INFO to request to report information about a USB device and the hub to which the device is attached. 





IOCTL_GET_HCD_DRIVERKEY_NAME



The IOCTL_GET_HCD_DRIVERKEY_NAME I/O control request retrieves the driver key name in the registry for a USB host controller driver.





IOCTL_USB_GET_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC







IOCTL_INTERNAL_USB_CYCLE_PORT



The IOCTL_INTERNAL_USB_CYCLE_PORT I/O request simulates a device unplug and replug on the port associated with the PDO. 
Drivers should cancel all I/O requests and wait for them to complete before initiating this operation. 
A driver that manages an individual interface on a composite device cannot cycle the port to which the device is attached without affecting the entire composite device and all of its interfaces. For this reason, drivers that manage interfaces should attempt other types of error recovery, such as resetting pipes (_URB_PIPE_REQUEST), before cycling the port. 

IOCTL_INTERNAL_USB_CYCLE_PORT is a kernel-mode I/O control request. This request targets the USB hub PDO. This request must be sent at an IRQL of PASSIVE_LEVEL.





IOCTL_INTERNAL_USB_ENABLE_PORT



The IOCTL_INTERNAL_USB_ENABLE_PORT IOCTL has been deprecated. Do not use.





IOCTL_INTERNAL_USB_GET_BUS_INFO



The IOCTL_INTERNAL_USB_GET_BUS_INFO I/O request queries the bus driver for certain bus information. 

IOCTL_INTERNAL_USB_GET_BUS_INFO is a kernel-mode I/O control request. This request targets the USB hub PDO. This request must be sent at an IRQL of PASSIVE_LEVEL.





IOCTL_INTERNAL_USB_GET_BUSGUID_INFO



 The IOCTL_INTERNAL_USB_GET_BUSGUID_INFO IOCTL has been deprecated. Do not use.





IOCTL_INTERNAL_USB_GET_CONTROLLER_NAME



The IOCTL_INTERNAL_USB_GET_CONTROLLER_NAME I/O request queries the bus driver for the device name of the USB host controller. 

IOCTL_INTERNAL_USB_GET_CONTROLLER_NAME is a kernel-mode I/O control request. This request targets the USB hub PDO. This request must be sent at an IRQL of PASSIVE_LEVEL.





IOCTL_INTERNAL_USB_GET_DEVICE_CONFIG_INFO



The IOCTL_INTERNAL_USB_GET_DEVICE_CONFIG_INFO 
   I/O request returns information about a USB device and the hub it is attached to.


IOCTL_INTERNAL_USB_GET_DEVICE_CONFIG_INFO is a kernel-mode I/O control request. This request targets the USB hub PDO. This request must be sent at an IRQL of DISPATCH_LEVEL or lower.





IOCTL_INTERNAL_USB_GET_DEVICE_HANDLE



 The IOCTL_INTERNAL_USB_GET_DEVICE_HANDLE IOCTL is used by the USB hub driver. Do not use.





IOCTL_INTERNAL_USB_GET_DEVICE_HANDLE_EX



 The IOCTL_INTERNAL_USB_GET_DEVICE_HANDLE_EX IOCTL is used by the USB hub driver. Do not use.





IOCTL_INTERNAL_USB_GET_HUB_COUNT



 The IOCTL_INTERNAL_USB_GET_HUB_COUNT IOCTL is used by the USB hub driver. Do not use.





IOCTL_INTERNAL_USB_GET_HUB_NAME



The IOCTL_INTERNAL_USB_GET_HUB_NAME I/O request is used by drivers to retrieve the UNICODE symbolic name for the target PDO if the PDO is for a hub. Otherwise a NULL string is returned. 
Drivers can use the symbolic name to retrieve additional information about the hub through user-mode I/O control requests and WMI calls.

IOCTL_INTERNAL_USB_GET_HUB_NAME is a kernel-mode I/O control request. This request targets the USB hub PDO. This request must be sent at an IRQL of PASSIVE_LEVEL.





IOCTL_INTERNAL_USB_GET_PARENT_HUB_INFO



The IOCTL_INTERNAL_USB_GET_PARENT_HUB_INFO 
   is used by the USB hub driver. Do not use.





IOCTL_INTERNAL_USB_GET_PORT_STATUS



The IOCTL_INTERNAL_USB_GET_PORT_STATUS I/O request queries the status of the PDO. 

IOCTL_INTERNAL_USB_GET_PORT_STATUS is a kernel-mode I/O control request. This request targets the USB hub PDO. This IOCTL must be sent at IRQL = PASSIVE_LEVEL.





IOCTL_INTERNAL_USB_GET_ROOTHUB_PDO



 The IOCTL_INTERNAL_USB_GET_ROOTHUB_PDO IOCTL is used by the USB hub driver. Do not use.





IOCTL_INTERNAL_USB_GET_TOPOLOGY_ADDRESS



The IOCTL_INTERNAL_USB_GET_TOPOLOGY_ADDRESS 
   I/O request returns information about the host controller the USB device is attached to, and the device's location in the USB device tree.

IOCTL_INTERNAL_USB_GET_TOPOLOGY_ADDRESS is a kernel-mode I/O control request. This request targets the USB hub PDO. This request must be sent at an IRQL of DISPATCH_LEVEL or lower.





IOCTL_INTERNAL_USB_GET_TT_DEVICE_HANDLE



 The IOCTL_INTERNAL_USB_GET_TT_DEVICE_HANDLE is used by the USB hub driver. Do not use.





IOCTL_INTERNAL_USB_NOTIFY_IDLE_READY



 The IOCTL_INTERNAL_USB_NOTIFY_IDLE_READY IOCTL is used by the USB hub driver. Do not use.





IOCTL_INTERNAL_USB_RECORD_FAILURE



 The IOCTL_INTERNAL_USB_RECORD_FAILURE IOCTL is used by the USB hub driver. Do not use.





IOCTL_INTERNAL_USB_REGISTER_COMPOSITE_DEVICE



The IOCTL_INTERNAL_USB_REGISTER_COMPOSITE_DEVICE 
   I/O request registers the driver of a USB  multi-function device (composite driver) with the underlying USB driver stack.





IOCTL_INTERNAL_USB_REQ_GLOBAL_RESUME



 The IOCTL_INTERNAL_USB_REQ_GLOBAL_RESUME IOCTL is used by the USB hub driver. Do not use.





IOCTL_INTERNAL_USB_REQ_GLOBAL_SUSPEND



 The IOCTL_INTERNAL_USB_REQ_GLOBAL_SUSPEND IOCTL is used by the USB hub driver. Do not use.





IOCTL_INTERNAL_USB_RESET_PORT



The IOCTL_INTERNAL_USB_RESET_PORT  I/O control request is used by a driver to reset the upstream port of the device it manages. After a successful reset, the bus driver reselects the configuration and any alternative interface settings that the device had before the reset occurred. All pipe handles, configuration handles and interface handles remain valid.
Drivers should cancel all I/O requests and wait for them to complete before initiating this operation. 
A driver that manages an individual interface on a composite device cannot reset the interface without resetting the entire composite device and all of its interfaces. For this reason, drivers that manage interfaces should attempt other types of error recovery, such as resetting pipes (_URB_PIPE_REQUEST), before resetting the interface. 
This IOCTL must be sent at an IRQL of PASSIVE_LEVEL.

IOCTL_INTERNAL_USB_RESET_PORT is a kernel-mode I/O control request. This request targets the USB hub PDO.





IOCTL_INTERNAL_USB_SUBMIT_IDLE_NOTIFICATION



The IOCTL_INTERNAL_USB_SUBMIT_IDLE_NOTIFICATION I/O request is used by drivers to inform the USB bus driver that a device is idle and can be suspended. 
When sending this IOCTL, caller must furnish a callback routine that does the actual suspension of the device. The USB bus driver will call this routine at PASSIVE_LEVEL when it is safe for the device to be powered down. If the device supports remote wake up and has no Wait/Wake IRP already pending, the callback routine should submit a Wait/Wake IRP to the bus driver for the device, before powering it down. 
For additional information, see Supporting Devices that Have Wake-Up Capabilities


IOCTL_INTERNAL_USB_SUBMIT_IDLE_NOTIFICATION is a kernel-mode I/O control request. This request targets the USB hub PDO. This request must be sent at an IRQL of PASSIVE_LEVEL.





IOCTL_INTERNAL_USB_SUBMIT_URB



The IOCTL_INTERNAL_USB_SUBMIT_URB I/O control request is used by drivers to submit an URB to the bus driver. 

IOCTL_INTERNAL_USB_SUBMIT_URB is a kernel-mode I/O control request. This request targets the USB hub PDO.





IOCTL_INTERNAL_USB_UNREGISTER_COMPOSITE_DEVICE



The IOCTL_INTERNAL_USB_UNREGISTER_COMPOSITE_DEVICE 
   I/O request unregisters the  driver of a USB multi-function device (composite driver) and releases all resources that are associated with registration. The request is successful only if the composite driver was previously registered with the underlying USB driver stack through the IOCTL_INTERNAL_USB_REGISTER_COMPOSITE_DEVICE request.





IOCTL_INTERNAL_USB_REQUEST_REMOTE_WAKE_NOTIFICATION



The IOCTL_INTERNAL_USB_REQUEST_REMOTE_WAKE_NOTIFICATION 
   I/O request is sent by the driver of a Universal Serial Bus (USB) multi-function device (composite driver) to request remote wake-up notifications from a specific function in the device.

IOCTL_INTERNAL_USB_REQUEST_REMOTE_WAKE_NOTIFICATION is a kernel-mode I/O control request. This request targets the USB hub physical device object (PDO). 





IOCTL_USB_DIAG_IGNORE_HUBS_OFF



The IOCTL_USB_DIAG_IGNORE_HUBS_OFF I/O control has been deprecated. Do not use.  





IOCTL_USB_DIAG_IGNORE_HUBS_ON



The IOCTL_USB_DIAG_IGNORE_HUBS_ON I/O control has been deprecated. Do not use.





IOCTL_USB_DIAGNOSTIC_MODE_OFF



The IOCTL_USB_DIAGNOSTIC_MODE_OFF I/O control has been deprecated. Do not use.





IOCTL_USB_DIAGNOSTIC_MODE_ON



The IOCTL_USB_DIAGNOSTIC_MODE_ON I/O control has been deprecated. Do not use.





IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION



The IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION I/O control request retrieves one or more descriptors for the device that is associated with the indicated port index.

IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION is a user-mode I/O control request. This request targets the USB hub device (GUID_DEVINTERFACE_USB_HUB).





IOCTL_USB_GET_DEVICE_CHARACTERISTICS



The client driver sends this request to determine general characteristics about a USB device, such as maximum send and receive delays for any request.





IOCTL_USB_GET_HUB_CAPABILITIES



The IOCTL_USB_GET_HUB_CAPABILITIES I/O control request retrieves the capabilities of a USB hub. Note  This request is replaced by IOCTL_USB_GET_HUB_CAPABILITIES_EX in Windows Vista.


IOCTL_USB_GET_HUB_CAPABILITIES  is a user-mode I/O control request. This request targets the USB hub device (GUID_DEVINTERFACE_USB_HUB).





IOCTL_USB_GET_HUB_CAPABILITIES_EX



The IOCTL_USB_GET_HUB_CAPABILITIES_EX I/O control request retrieves the capabilities of a USB hub.

IOCTL_USB_GET_HUB_CAPABILITIES_EX is a user-mode I/O control request. This request targets the USB hub device (GUID_DEVINTERFACE_USB_HUB).





IOCTL_USB_GET_HUB_INFORMATION_EX



The IOCTL_USB_GET_HUB_INFORMATION_EX I/O control request is sent by an application to retrieve information about a USB hub in a USB_HUB_INFORMATION_EX structure.
The request retrieves the highest port number on the hub. For USB 2.0 and SuperSpeed hubs (non-root hubs), the request also retrieves the associated hub descriptors, as defined in USB 2.0 and 3.0 Specifications, respectively. 

IOCTL_USB_GET_HUB_INFORMATION_EX is a user-mode I/O control request. This request targets the USB hub device (GUID_DEVINTERFACE_USB_HUB).





IOCTL_USB_GET_NODE_CONNECTION_ATTRIBUTES



The IOCTL_USB_GET_NODE_CONNECTION_ATTRIBUTES I/O control request retrieves the Microsoft-extended port attributes for a specific port. 

IOCTL_USB_GET_NODE_CONNECTION_ATTRIBUTES is a user-mode I/O control request. This request targets the USB hub device (GUID_DEVINTERFACE_USB_HUB).





IOCTL_USB_GET_NODE_CONNECTION_DRIVERKEY_NAME



The IOCTL_USB_GET_NODE_CONNECTION_DRIVERKEY_NAME I/O control request retrieves the driver registry key name that is associated with the device that is connected to the indicated port. 

IOCTL_USB_GET_NODE_CONNECTION_DRIVERKEY_NAME is a user-mode I/O control request. This request targets the USB hub device (GUID_DEVINTERFACE_USB_HUB).





IOCTL_USB_GET_NODE_CONNECTION_INFORMATION



The IOCTL_USB_GET_NODE_CONNECTION_INFORMATION request retrieves information about the indicated USB port and the device that is attached to the port, if there is one.
Client drivers must send this IOCTL at an IRQL of PASSIVE_LEVEL.

IOCTL_USB_GET_NODE_CONNECTION_INFORMATION is a user-mode I/O control request. This request targets the USB hub device (GUID_DEVINTERFACE_USB_HUB). Do not send this request to the root hub.





IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX



The IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX request retrieves information about a USB port and the device that is attached to the port, if there is one.
Client drivers must send this IOCTL at an IRQL of PASSIVE_LEVEL.

IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX is a user-mode I/O control request. This request targets the USB hub device (GUID_DEVINTERFACE_USB_HUB). Do not send this request to the root hub.





IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX_V2



The IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX_V2 I/O control is sent by an application to retrieve information about the protocols that are supported by a particular USB port on a hub. The request also retrieves the speed capability of the port.





IOCTL_USB_GET_NODE_CONNECTION_NAME



The IOCTL_USB_GET_NODE_CONNECTION_NAME I/O control request is used with the USB_NODE_CONNECTION_NAME structure to retrieve the symbolic link name of the hub that is attached to the downstream port.

IOCTL_USB_GET_NODE_CONNECTION_NAME is a user-mode I/O control request. This request targets the USB hub device (GUID_DEVINTERFACE_USB_HUB).





IOCTL_USB_GET_NODE_INFORMATION



The IOCTL_USB_GET_NODE_INFORMATION I/O control request is used with the USB_NODE_INFORMATION structure to retrieve information about a parent device.

IOCTL_USB_GET_NODE_INFORMATION is a user-mode I/O control request. This request targets the USB hub device (GUID_DEVINTERFACE_USB_HUB).





IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES



The IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES I/O control request is sent by an application to retrieve information about a specific port on a USB hub. 

IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES is a user-mode I/O control request. This request targets the USB hub device (GUID_DEVINTERFACE_USB_HUB).





IOCTL_USB_GET_ROOT_HUB_NAME



The IOCTL_USB_GET_ROOT_HUB_NAME I/O control request is used with the USB_ROOT_HUB_NAME structure to retrieve the symbolic link name of the root hub.

IOCTL_USB_GET_ROOT_HUB_NAME is a user-mode I/O control request. This request targets the USB host controller (GUID_DEVINTERFACE_USB_HOST_CONTROLLER).





IOCTL_USB_GET_TRANSPORT_CHARACTERISTICS



The client driver sends this request to retrieve the transport characteristics.





IOCTL_USB_HCD_DISABLE_PORT



The IOCTL_USB_HCD_DISABLE_PORT IOCTL has been deprecated. Do not use.





IOCTL_USB_HCD_ENABLE_PORT



The IOCTL_USB_HCD_ENABLE_PORT IOCTL has been deprecated. Do not use.





IOCTL_USB_HCD_GET_STATS_1



The IOCTL_USB_HCD_GET_STATS_1 IOCTL has been deprecated. Do not use.





IOCTL_USB_HCD_GET_STATS_2



The IOCTL_USB_HCD_GET_STATS_2 IOCTL has been deprecated. Do not use.





IOCTL_USB_HUB_CYCLE_PORT



The IOCTL_USB_HUB_CYCLE_PORT I/O control request power-cycles the port that is associated with the PDO that receives the request. 

IOCTL_USB_HUB_CYCLE_PORT is a user-mode I/O control request. This request targets the USB hub device (GUID_DEVINTERFACE_USB_HUB).





IOCTL_USB_NOTIFY_ON_TRANSPORT_CHARACTERISTICS_CHANGE



This request notifies the caller of change in transport characteristics.  





IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE



This request registers for notifications about the changes in transport characteristics. 





IOCTL_USB_RESET_HUB



The IOCTL_USB_RESET_HUB IOCTL is used by the USB driver stack.  Do not use.





IOCTL_USB_START_TRACKING_FOR_TIME_SYNC



This request registers the caller with USB driver stack for time sync services. 





IOCTL_USB_STOP_TRACKING_FOR_TIME_SYNC



This request unegisters the caller with USB driver stack for time sync services. 





IOCTL_USB_UNREGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE



This request unregisters the caller from getting notifications about transport characteristics changes.





USB_CONNECTION_STATUS



The USB_CONNECTION_STATUS enumerator indicates the status of the connection to a device on a USB hub port.





USB_DESCRIPTOR_REQUEST



The USB_DESCRIPTOR_REQUEST structure is used with the IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION I/O control request to retrieve one or more descriptors for the device that is associated with the indicated connection index.





USB_DEVICE_CHARACTERISTICS



Contains information about the USB device’s characteristics, such as the maximum send and receive delays for any request.  This structure is used in the IOCTL_USB_GET_DEVICE_CHARACTERISTICS request.





USB_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC_INFORMATION



Stores the frame and microframe numbers and the calculated system QPC values. This structure is used in the IOCTL_USB_GET_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC request.





USB_HCD_DRIVERKEY_NAME



The USB_HCD_DRIVERKEY_NAME structure is used with the IOCTL_GET_HCD_DRIVERKEY_NAME I/O control request to retrieve the driver key in the registry for the USB host controller driver.





USB_HUB_CAP_FLAGS



The USB_HUB_CAP_FLAGS structure is used to report the capabilities of a hub.





USB_HUB_CAPABILITIES



The USB_HUB_CAPABILITIES structure has been deprecated. Use USB_HUB_CAPABILITIES_EX instead.





USB_HUB_INFORMATION_EX



The USB_HUB_INFORMATION_EX structure is used with the IOCTL_USB_GET_HUB_INFORMATION_EX I/O control request to retrieve information about a  USB hub.





USB_HUB_CAPABILITIES_EX



The USB_HUB_CAPABILITIES_EX structure is used with the IOCTL_USB_GET_HUB_CAPABILITIES I/O control request to retrieve the capabilities of a particular USB hub.





USB_HUB_INFORMATION



The USB_HUB_INFORMATION structure contains information about a hub.





USB_HUB_NAME



The USB_HUB_NAME structure stores the hub's symbolic device name.





USB_HUB_NODE



The USB_HUB_NODE enumerator indicates whether a device is a hub or a composite device.





USB_HUB_TYPE



The USB_HUB_TYPE enumeration defines constants that indicate the type of USB hub.

The hub type is retrieved by the IOCTL_USB_GET_HUB_INFORMATION_EX I/O control request.





USB_ID_STRING



The USB_ID_STRING structure is used to store a string or multi-string.





USB_MI_PARENT_INFORMATION



The USB_MI_PARENT_INFORMATION structure contains information about a composite device.





USB_NODE_CONNECTION_INFORMATION_EX_V2



The USB_NODE_CONNECTION_INFORMATION_EX_V2 structure is used with the IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX_V2 I/O control request to retrieve speed information about a USB device that is attached to a particular port.





USB_NODE_CONNECTION_ATTRIBUTES



The USB_NODE_CONNECTION_ATTRIBUTES structure is used with the IOCTL_USB_GET_NODE_CONNECTION_ATTRIBUTES I/O control request to retrieve the attributes of a connection.





USB_NODE_CONNECTION_DRIVERKEY_NAME



The USB_NODE_CONNECTION_DRIVERKEY_NAME structure is used with the IOCTL_USB_GET_NODE_CONNECTION_DRIVERKEY_NAME I/O control request to retrieve the driver key name for the device that is connected to the indicated port.





USB_NODE_CONNECTION_INFORMATION



The USB_NODE_CONNECTION_INFORMATION structure is used with the IOCTL_USB_GET_NODE_CONNECTION_INFORMATION  request to retrieve information about a USB port and connected device.





USB_NODE_CONNECTION_INFORMATION_EX



The USB_NODE_CONNECTION_INFORMATION_EX structure is used in conjunction with the IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX request to obtain information about the connection associated with the indicated USB port.





USB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS



The USB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS union is used to indicate the speed at which a USB 3.0  device is currently operating and whether it can operate at higher speed, when attached to a particular port. 
Device speed information is obtained in the USB_NODE_CONNECTION_INFORMATION_EX_V2 structure by the IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX_V2 I/O control request.
Or: the speed in which a device attached to a port is currently operating and at what speeds it is capable of operating.





USB_NODE_CONNECTION_NAME



The USB_NODE_CONNECTION_NAME structure is used with the IOCTL_USB_GET_NODE_CONNECTION_NAME I/O control request to retrieve the symbolic link of the downstream hub that is attached to the port.





USB_NODE_INFORMATION



The USB_NODE_INFORMATION structure is used with the IOCTL_USB_GET_NODE_INFORMATION I/O control request to retrieve information about a parent device.





USB_PIPE_INFO



The USB_PIPE_INFO structure is used in conjunction with the USB_NODE_CONNECTION_INFORMATION_EX structure and the IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX request to obtain information about a connection and its associated pipes.





USB_PORT_CONNECTOR_PROPERTIES



The USB_PORT_CONNECTOR_PROPERTIES structure is used with the IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES I/O control request to retrieve information about a port on a particular SuperSpeed hub.





USB_PORT_PROPERTIES



The USB_PORT_PROPERTIES union is used to report the capabilities of a USB port.
The  port capabilities are retrieved in the USB_PORT_CONNECTOR_PROPERTIES structure by the IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES I/O control request.





USB_PROTOCOLS



The USB_PROTOCOLS union is used to report the USB signaling protocols that are supported by the port.





USB_ROOT_HUB_NAME



The USB_ROOT_HUB_NAME structure stores the root hub's symbolic device name.





USB_START_TRACKING_FOR_TIME_SYNC_INFORMATION



The input and output buffer for the IOCTL_USB_START_TRACKING_FOR_TIME_SYNC request.





USB_STOP_TRACKING_FOR_TIME_SYNC_INFORMATION



The input buffer for the IOCTL_USB_STOP_TRACKING_FOR_TIME_SYNC request.





USB_TOPOLOGY_ADDRESS



The USB_TOPOLOGY_ADDRESS structure is used with the IOCTL_INTERNAL_USB_GET_TOPOLOGY_ADDRESS I/O request to retrieve information about a USB device?s location in the USB device tree. 





USB_TRANSPORT_CHARACTERISTICS



Stores the transport characteristics at relevant points in time. This structure is used in the  IOCTL_USB_GET_TRANSPORT_CHARACTERISTICS request.





USB_TRANSPORT_CHARACTERISTICS_CHANGE_NOTIFICATION



Contains registration information filled when the IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE 

request completes.





USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION



Contains registration information for the IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE 

request.





USB_TRANSPORT_CHARACTERISTICS_CHANGE_UNREGISTRATION



Contains unregistration information for the IOCTL_USB_UNREGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE 

request.



 


## Deprecated and Reserved USB IOCTLs

The following I/O requests have been deprecated or reserved for internal use.  USB client drivers must not use these I/O requests:

- 
IOCTL_USB_DIAG_IGNORE_HUBS_OFF

- 
IOCTL_USB_DIAG_IGNORE_HUBS_ON

- 
IOCTL_USB_DIAGNOSTIC_MODE_OFF

- 
IOCTL_USB_DIAGNOSTIC_MODE_ON

- 
IOCTL_USB_GET_HUB_CAPABILITIES

- 
IOCTL_USB_HCD_DISABLE_PORT

- 
IOCTL_USB_HCD_ENABLE_PORT

- 
IOCTL_USB_HCD_GET_STATS_1

- 
IOCTL_USB_HCD_GET_STATS_2

- 
IOCTL_USB_RESET_HUB


Send comments about this topic to Microsoft

