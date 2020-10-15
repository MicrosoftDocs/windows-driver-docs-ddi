---
UID: TP:hid
title: Human Interface Devices (HID)
ms.assetid: 87c002be-da96-313a-bae1-c6a49c9ce065
ms.date: 05/09/2018
keywords: ["Human Interface Devices (HID)"]
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Human Interface Devices (HID)

## -description

Overview of the Human Interface Devices (HID) technology.

To develop Human Interface Devices (HID), you need these headers:

* [hidclass.h](../hidclass/index.md)

* [hidpddi.h](../hidpddi/index.md)

* [hidpi.h](../hidpi/index.md)

* [hidport.h](../hidport/index.md)

* [hidsdi.h](../hidsdi/index.md)

* [kbdmou.h](../kbdmou/index.md)

* [ntdd8042.h](../ntdd8042/index.md)

* [vhf.h](../vhf/index.md)

For the programming guide, see [Human Interface Devices (HID)](/windows-hardware/drivers/hid).

This section contains the programming interfaces related to Human Interface Devices (or HID). Typically, these are devices that humans use to directly control the operation of computer systems.

## HIDClass Support Routines

There are system-supplied routines that user-mode applications, kernel-mode drivers, and HID minidrivers use to operate devices in the HIDClass device setup class.

As a general rule, user-mode applications can use the HidD_Xxx and HidP_Xxx routines. However, kernel-mode drivers can only call HidP_Xxx routines. 

HID minidrivers use only the **HidRegisterMinidriver** routine.

For Windows 8.1 Microsoft introduced the new Windows.Devices.HumanInterfaceDevice API which lets you write Windows apps that access HID devices.

The header defines IOCTLs that a HID minidriver must support. Only the HID class driver sends these IOCTLs to a HID minidriver. User-mode applications and other kernel-mode drivers can only communicate with HID collections by using the HIDClass support routines and HID class driver ioctls.

## HID Minidriver IOCTLs

A HID minidriver must handle a set of IOCTLs. Only the HID class driver sends these IOCTLs to a HID minidriver. User-mode applications and other kernel-mode drivers can only communicate with HID collections by using the HIDClass support routines and HID class driver ioctls.

|Topic | Description |
|---|---|
|IOCTL_HID_ACTIVATE_DEVICE| The IOCTL_HID_ACTIVATE_DEVICE request activates a HIDClass device, which makes it ready for I/O operations.|
|IOCTL_HID_DEACTIVATE_DEVICE| The IOCTL_HID_DEACTIVATE_DEVICE request deactivates a HIDClass device, which causes it to stop operations and terminate all outstanding I/O requests.|
|IOCTL_HID_GET_DEVICE_ATTRIBUTES| The IOCTL_HID_GET_DEVICE_ATTRIBUTES request obtains a HIDClass device's attributes in a HID_DEVICE_ATTRIBUTES structure.|
|IOCTL_HID_GET_DEVICE_DESCRIPTOR| The IOCTL_HID_GET_DEVICE_DESCRIPTOR request obtains a HIDClass device's HID descriptor.|
|IOCTL_HID_GET_REPORT_DESCRIPTOR| The IOCTL_HID_GET_REPORT_DESCRIPTOR request obtains the report descriptor for a HIDClass device.|
|IOCTL_HID_GET_STRING| The IOCTL_HID_GET_STRING request obtains a manufacturer ID, product ID, or serial number for a top-level collection. The retrieved string is a NULL-terminated wide character string in a human-readable format.|
|IOCTL_HID_READ_REPORT| The IOCTL_HID_READ_REPORT request transfers an input report from a HIDClass device into the HID class driver's buffer.|
|IOCTL_HID_WRITE_REPORT| The IOCTL_HID_WRITE_REPORT request sends a HID report to a HIDClass device.|
|IOCTL_UMDF_GET_PHYSICAL_DESCRIPTOR| The IOCTL_UMDF_GET_PHYSICAL_DESCRIPTOR control code obtains the physical descriptor of a HIDClass device.|
|IOCTL_UMDF_HID_GET_FEATURE| The IOCTL_UMDF_HID_GET_FEATURE control code obtains a feature report from a HIDClass device.|
|IOCTL_UMDF_HID_GET_INPUT_REPORT| The IOCTL_UMDF_HID_GET_INPUT_REPORT control code returns an input report from a HIDClass device.|
|IOCTL_UMDF_HID_SET_FEATURE| The IOCTL_UMDF_HID_GET_FEATURE control code sends a feature report to a HIDClass device.|
|IOCTL_UMDF_HID_SET_OUTPUT_REPORT| The IOCTL_UMDF_HID_SET_OUTPUT_REPORT control code sends an output report to a top-level collection.|

## HID Class Driver IOCTLs

The HID class driver handles IOCTLs to support for top-level collections. 

Although user applications can communicate with the HID class driver by using HidD_Xxx  HIDClass support routines, kernel-mode drivers must send the corresponding device control requests described in this section.

The input and output parameters are request-specific.

Upon completion of a request, the I/O status block members are set as follows: 

The **Status** member is set by the HID class driver for all requests that it handles.

As described for each IOCTL, the Information member is set either by the class driver or a lower-level driver. Normally, when a lower-level driver transfers data from or to a device, the lower-level driver sets Information to the number of bytes transferred. However, the HID class driver might return a different value.

|Topic | Description |
|---|---|
|IOCTL_GET_NUM_DEVICE_INPUT_BUFFERS| The IOCTL_GET_NUM_DEVICE_INPUT_BUFFERS request obtains the size of the input report queue for a top-level collection. |
|IOCTL_GET_PHYSICAL_DESCRIPTOR | The IOCTL_GET_PHYSICAL_DESCRIPTOR request obtains the physical descriptor of a top-level collection.|
|IOCTL_HID_DEVICERESET_NOTIFICATION | The IOCTL_HID_DEVICERESET_NOTIFICATION request is sent by the HID client driver to HID class driver to wait for a device-initiated reset event.|
|IOCTL_HID_DISABLE_SECURE_READ | The IOCTL_HID_DISABLE_SECURE_READ request cancels an IOCTL_HID_ENABLE_SECURE_READ request for a HID collection.|
|IOCTL_HID_ENABLE_SECURE_READ | The IOCTL_HID_ENABLE_SECURE_READ request enables a secure read for open files of a HID collection.|
|IOCTL_HID_ENABLE_WAKE_ON_SX | The IOCTL_HID_ENABLE_WAKE_ON_SX request is used to indicate the requirement for a device to be able to wake from system sleep.|
|IOCTL_HID_FLUSH_QUEUE| The IOCTL_HID_FLUSH_QUEUE request dequeues all of the unparsed input reports from a top-level collection's input report queue. |
|IOCTL_HID_GET_COLLECTION_DESCRIPTOR| The IOCTL_HID_GET_COLLECTION_DESCRIPTOR request obtains a top-level collection's preparsed data, which the HID class driver extracted from the physical device's report descriptor during device initialization.|
|IOCTL_HID_GET_COLLECTION_INFORMATION| The IOCTL_HID_GET_COLLECTION_INFORMATION request obtains a top-level collection's HID_COLLECTION_INFORMATION structure.|
|IOCTL_HID_GET_DRIVER_CONFIG| The IOCTL_HID_GET_DRIVER_CONFIG request retrieves the driver configuration.|
|IOCTL_HID_GET_FEATURE| The IOCTL_HID_GET_FEATURE request returns a feature report associated with a top-level collection.|
|IOCTL_HID_GET_HARDWARE_ID | The IOCTL_HID_GET_HARDWARE_ID request obtains the Plug and Play hardware ID of a top-level collection.| 
|IOCTL_HID_GET_INDEXED_STRING | The IOCTL_HID_GET_INDEXED_STRING request obtains a specified embedded string from a top-level collection. |
|IOCTL_HID_GET_INPUT_REPORT | The IOCTL_HID_GET_INPUT_REPORT request obtains an input report from a top-level collection.|
|IOCTL_HID_GET_MANUFACTURER_STRING | The IOCTL_HID_GET_MANUFACTURER_STRING request obtains a top-level collection's embedded string that identifies the manufacturer of the device.|
|IOCTL_HID_GET_MS_GENRE_DESCRIPTOR | The IOCTL_HID_GET_MS_GENRE_DESCRIPTOR request is used for retrieving the genre descriptor for the device.|
|IOCTL_HID_GET_POLL_FREQUENCY_MSEC | The IOCTL_HID_GET_POLL_FREQUENCY_MSEC request obtains the current polling frequency, in milliseconds, of a top-level collection.|
|IOCTL_HID_GET_PRODUCT_STRING| The IOCTL_HID_GET_PRODUCT_STRING request obtains a top-level collection's embedded string that identifies the manufacturer's product. The retrieved string is a NULL-terminated wide character string in a human-readable format. For general information about HIDClass devices, see HID Collections. 
|IOCTL_HID_GET_SERIALNUMBER_STRING| The IOCTL_HID_GET_SERIALNUMBER_STRING request obtains a top-level collection's embedded string that identifies the device's serial number.|
|IOCTL_HID_SET_DRIVER_CONFIG| The IOCTL_HID_SET_DRIVER_CONFIG request sets the driver configuration.|
|IOCTL_HID_SET_FEATURE| The IOCTL_HID_SET_FEATURE request sends a feature report to a top-level collection. For general information about HIDClass devices, see HID Collections. |
|IOCTL_HID_SET_OUTPUT_REPORT| The IOCTL_HID_SET_OUTPUT_REPORT request sends an output report to a top-level collection.|
|IOCTL_HID_SET_POLL_FREQUENCY_MSEC| The IOCTL_HID_SET_POLL_FREQUENCY_MSEC request sets the polling frequency, in milliseconds, for a top-level collection. User-mode applications or kernel-mode drivers that perform irregular, opportunistic reads on a polled device must furnish a polling interval of zero. In such cases, IOCTL_HID_SET_POLL_FREQUENCY_MSEC does not actually change the polling frequency of the device; but if the report data is not stale when it is read, the read is completed immediately with the latest report data for the indicated collection. If the report data is stale, it is refreshed immediately, without waiting for the expiration of the polling interval, and the read is completed with the new data. If the value for the polling interval that is provided in the IRP is not zero, it must be >= MIN_POLL_INTERVAL_MSEC and <= MAX_POLL_INTERVAL_MSEC. Polling may be limited if there are multiple top-level collections. For general information about HIDClass devices, see HID Collections. |
|IOCTL_HID_SET_S0_IDLE_TIMEOUT| The IOCTL_HID_SET_S0_IDLE_TIMEOUT request is used by a client to inform the HID class driver about the client's preferred idle timeout value.|
|IOCTL_SET_NUM_DEVICE_INPUT_BUFFERS| The IOCTL_SET_NUM_DEVICE_INPUT_BUFFERS request sets the number of buffers for the input report queue of a top-level collection. Each input report queue is implemented as a ring buffer. If a collection transmits data to the HID class driver faster than the driver can read it, some of the data may be lost. To prevent this type of loss, you can use an IOCTL_SET_NUM_DEVICE_INPUT_BUFFERS request to adjust the number of buffers that the input report queue contains. The HID class driver requires a minimum of two input buffers. The maximum number of input buffers that the HID class driver supports is 512. The default number of input buffers is 32. For general information about HIDClass devices, see HID Collections. |

## Reserved for internal system use.

This section lists, in alphabetical order, the HIDClass-related routines, structures, enumeration types and data types that are reserved for internal system use.

* DeviceObjectState

* HID_DRIVER_CONFIG

* HID_INTERFACE_HIDPARSE

* HID_INTERFACE_NOTIFY_PNP

* HIDD_CONFIGURATION

* HidD_GetConfiguration

* HidD_GetMsGenreDescriptor

* HidD_SetConfiguration

* HIDP_COLLECTION_DESC

* HIDP_DEVICE_DESC

* HidP_FreeCollectionDescription

* HIDP_GETCOLDESC_DBG

* HIDP_KEYBOARD_DIRECTION

* HIDP_KEYBOARD_MODIFIER_STATE

* HIDP_REPORT_IDS

* HidP_SysPowerCaps

* HidP_SysPowerEvent

* HidP_TranslateUsageAndPagesToI8042ScanCodes

* PHID_STATUS_CHANGE

* PHIDP_INSERT_SCANCODES

* PHIDP_REPORT_DESCRIPTOR

### DeviceObjectState

The DeviceObjectState enumeration type is reserved for internal system use.

```cpp 
enum DeviceObjectState {
  DeviceObjectStarted,
  DeviceObjectStopped,
  DeviceObjectRemoved
};
```
Headers
Declared in Hidclass.h.

### HID_DRIVER_CONFIG
The HID_DRIVER_CONFIG structure is reserved for internal system use.

```cpp
typedef struct _HID_DRIVER_CONFIG {
  ULONG  Size;
  ULONG  RingBufferSize;
} HID_DRIVER_CONFIG, *PHID_DRIVER_CONFIG;
```

Headers
Declared in Hidclass.h.

### HID_INTERFACE_HIDPARSE

The HID_INTERFACE_HIDPARSE structure is reserved for internal system use.

```cpp
typedef struct _HID_INTERFACE_HIDPARSE {
#ifndef __cplusplus
  INTERFACE;
#else
  INTERFACE  i;
#endif
  PHIDP_GETCAPS  HidpGetCaps;
} HID_INTERFACE_HIDPARSE, *PHID_INTERFACE_HIDPARSE;
```

Headers
Declared in Hidclass.h.

### HID_INTERFACE_NOTIFY_PNP

The HID_INTERFACE_NOTIFY_PNP structure is reserved for internal system use.

```cpp
typedef struct _HID_INTERFACE_NOTIFY_PNP {
#ifndef __cplusplus
  INTERFACE;
#else
  INTERFACE  i;
#endif
  PHID_STATUS_CHANGE  StatusChangeFn;
  PVOID CallbackContext;
} HID_INTERFACE_NOTIFY_PNP, *PHID_INTERFACE_NOTIFY_PNP;
```

Headers
Declared in Hidclass.h.

### HIDD_CONFIGURATION

The HIDD_CONFIGURATION structure is reserved for internal system use.

```cpp
typedef struct _HIDD_CONFIGURATION {
  PVOID  cookie;
  ULONG  size;
  ULONG  RingBufferSize;
} HIDD_CONFIGURATION, *PHIDD_CONFIGURATION;
```

Headers
Declared in Hidsdi.h.

### HidD_GetConfiguration

The HidD_GetConfiguration routine is reserved for internal system use.

```cpp
BOOLEAN __stdcall
HidD_GetConfiguration(
    IN HANDLE  HidDeviceObject,
    OUT PHIDD_CONFIGURATION  Configuration,
    IN ULONG  ConfigurationLength
    );
```

Headers
Declared in Hidsdi.h.

### HidD_GetMsGenreDescriptor

The HidD_GetMsGenreDescriptor routine is reserved for internal system use.

```cpp
BOOLEAN __stdcall
HidD_GetMsGenreDescriptor(
    IN HANDLE  HidDeviceObject,
    OUT PVOID  Buffer,
    IN ULONG  BufferLength
    );
```

Headers
Declared in Hidsdi.h.

### HidD_SetConfiguration

The HidD_SetConfiguration routine is reserved for internal system use.

```cpp
BOOLEAN __stdcall
HidD_SetConfiguration(
    IN HANDLE  HidDeviceObject,
    IN PHIDD_CONFIGURATION  Configuration,
    IN ULONG  ConfigurationLength
    );
```

Headers
Declared in Hidsdi.h.

### HIDP_COLLECTION_DESC

The HIDP_COLLECTION_DESC structure is reserved for internal system use.

```cpp
typedef struct _HIDP_COLLECTION_DESC {
  USAGE  UsagePage;
  USAGE  Usage;
  UCHAR  CollectionNumber;
  UCHAR  Reserved [15];
  USHORT  InputLength;
  USHORT  OutputLength;
  USHORT  FeatureLength;
  USHORT  PreparsedDataLength;
  PHIDP_PREPARSED_DATA  PreparsedData;
} HIDP_COLLECTION_DESC, *PHIDP_COLLECTION_DESC;
```

Headers
Declared in Hidpddi.h.

### HIDP_DEVICE_DESC

The HIDP_DEVICE_DESC structure is reserved for internal system use.

```cpp
typedef struct _HIDP_DEVICE_DESC {
  PHIDP_COLLECTION_DESC  CollectionDesc;
  ULONG  CollectionDescLength;
  PHIDP_REPORT_IDS  ReportIDs;
  ULONG  ReportIDsLength;
  HIDP_GETCOLDESC_DBG  Dbg;
} HIDP_DEVICE_DESC, *PHIDP_DEVICE_DESC;
```

Headers
Declared in Hidpddi.h.

### HidP_FreeCollectionDescription

The HidP_FreeCollectionDescription routine is reserved for internal system use.

```cpp
VOID
HidP_FreeCollectionDescription(
    IN PHIDP_DEVICE_DESC  DeviceDescription
    );
```

Headers
Declared in Hidpddi.h.

### HIDP_GETCOLDESC_DBG

The HIDP_GETCOLDESC_DBG structure is reserved for internal system use.

```cpp
typedef struct _HIDP_GETCOLDESC_DBG {
  ULONG  BreakOffset;
  ULONG  ErrorCode;
  ULONG  Args[6];
} HIDP_GETCOLDESC_DBG, *PHIDP_GETCOLDESC_DBG;
```

Headers
Declared in Hidpddi.h.

### HIDP_KEYBOARD_DIRECTION

The HIDP_KEYBOARD_DIRECTION enumeration type is reserved for internal system use.

```cpp
typedef enum _HIDP_KEYBOARD_DIRECTION {
 HidP_Keyboard_Break,
 HidP_Keyboard_Make
} HIDP_KEYBOARD_DIRECTION;
```

Headers
Declared in Hidpi.h.

### HIDP_KEYBOARD_MODIFIER_STATE

The HIDP_KEYBOARD_MODIFIER_STATE structure is reserved for internal system use.

```cpp
typedef struct _HIDP_KEYBOARD_MODIFIER_STATE {
  union {
    struct {
      ULONG  LeftControl: 1;
      ULONG  LeftShift: 1;
      ULONG  LeftAlt: 1;
      ULONG  LeftGUI: 1;
      ULONG  RightControl: 1;
      ULONG  RightShift: 1;
      ULONG  RightAlt: 1;
      ULONG  RigthGUI: 1;
      ULONG  CapsLock: 1;
      ULONG  ScollLock: 1;
      ULONG  NumLock: 1;
      ULONG  Reserved: 21;
    };
    ULONG ul;
  };
} HIDP_KEYBOARD_MODIFIER_STATE, *PHIDP_KEYBOARD_MODIFIER_STATE;
```

Headers
Declared in Hidpi.h.

### HIDP_REPORT_IDS

The HIDP_REPORT_IDS structure is reserved for internal system use.

```cpp
typedef struct _HIDP_REPORT_IDS {
  UCHAR  ReportID;
  UCHAR  CollectionNumber;
  USHORT  InputLength;
  USHORT  OutputLength;
  USHORT  FeatureLength;
} HIDP_REPORT_IDS, *PHIDP_REPORT_IDS;
```

Headers
Declared in Hidpddi.h.

### HidP_SysPowerCaps

The HidP_SysPowerCaps routine is reserved for internal system use.

```cpp
NTSTATUS
HidP_SysPowerCaps(
    IN PHIDP_PREPARSED_DATA  Ppd,
    OUT PULONG  OutputBuffer
    );
```

Headers
Declared in Hidpddi.h.

### HidP_SysPowerEvent

The HidP_SysPowerEvent routine is reserved for internal system use.

```cpp
NTSTATUS
HidP_SysPowerEvent(
    IN PCHAR  HidPacket,
    IN USHORT  HidPacketLength,
    IN PHIDP_PREPARSED_DATA  Ppd,
    OUT PULONG  OutputBuffer
    );
```

Headers
Declared in Hidpddi.h.

### HidP_TranslateUsageAndPagesToI8042ScanCodes

The HidP_TranslateUsageAndPagesToI8042ScanCodes routine is reserved for internal system use.

```cpp
NTSTATUS __stdcall
  HidP_TranslateUsageAndPagesToI8042ScanCodes(
    IN PUSAGE_AND_PAGE  ChangedUsageList,
    IN ULONG  UsageListLength,
    IN HIDP_KEYBOARD_DIRECTION  KeyAction,
    IN OUT PHIDP_KEYBOARD_MODIFIER_STATE  ModifierState,
    IN PHIDP_INSERT_SCANCODES  InsertCodesProcedure,
    IN PVOID  InsertCodesContext
    );
```

Headers
Declared in Hidpi.h.

### PHID_STATUS_CHANGE

The PHID_STATUS_CHANGE routine is reserved for internal system use.

```cpp
typedef VOID (*PHID_STATUS_CHANGE)(
    PVOID  Context, 
    enum DeviceObjectState State
    );
```

Headers
Declared in Hidclass.h.

### PHIDP_INSERT_SCANCODES

The PHIDP_INSERT_SCANCODES routine is reserved for internal system use.

```cpp
typedef BOOLEAN (*PHIDP_INSERT_SCANCODES)(
    IN PVOID  Context,
    IN PCHAR  NewScanCodes,
    IN ULONG  Length
    );
```

Headers
Declared in Hidpi.h.

### PHIDP_REPORT_DESCRIPTOR

The PHIDP_REPORT_DESCRIPTOR data type is reserved for internal system use.

```cpp
typedef PUCHAR  PHIDP_REPORT_DESCRIPTOR;
```

Headers
Declared in Hidpi.h.



## Callback functions

| Title   | Description   |
| ---- |:---- |
| [EVT_VHF_ASYNC_OPERATION](../vhf/nc-vhf-evt_vhf_async_operation.md) | The HID source driver implements this event callback if it wants to support one of the four asynchronous operation to get and set HID reports. |
| [EVT_VHF_CLEANUP](../vhf/nc-vhf-evt_vhf_cleanup.md) | The HID source driver implements this event callback to free resources that might the driver allocated to the virtual HID device. |
| [EVT_VHF_READY_FOR_NEXT_READ_REPORT](../vhf/nc-vhf-evt_vhf_ready_for_next_read_report.md) | The HID source driver implements this event call back function to use its buffering scheme for HID Input Reports, and wants to get notified when the next report can be submitted to VHF. |
| [PHIDP_GETCAPS](../hidclass/nc-hidclass-phidp_getcaps.md) | The HidP_GetCaps routine returns a top-level collection's HIDP_CAPS structure. |
| [PI8042_ISR_WRITE_PORT](../ntdd8042/nc-ntdd8042-pi8042_isr_write_port.md) | The PI8042_ISR_WRITE_PORT-typed callback routine writes data to an i8042 port. I8042prt provides this callback. |
| [PI8042_KEYBOARD_INITIALIZATION_ROUTINE](../ntdd8042/nc-ntdd8042-pi8042_keyboard_initialization_routine.md) | A PI8042_KEYBOARD_INITIALIZATION_ROUTINE-typed callback routine supplements the default initialization of a keyboard device by I8042prt. |
| [PI8042_KEYBOARD_ISR](../ntdd8042/nc-ntdd8042-pi8042_keyboard_isr.md) | A PI8042_KEYBOARD_ISR-typed callback routine customizes the operation of the I8042prt keyboard ISR. |
| [PI8042_MOUSE_ISR](../ntdd8042/nc-ntdd8042-pi8042_mouse_isr.md) | A PI8042_MOUSE_ISR-typed callback routine customizes the operation of the I8042prt mouse ISR. |
| [PI8042_QUEUE_PACKET](../ntdd8042/nc-ntdd8042-pi8042_queue_packet.md) | The PI8042_QUEUE_PACKET-typed callback routine queues an input data packet for processing by the ISR DPC of a keyboard or mouse device. I8042prt provides this callback. |
| [PI8042_SYNCH_READ_PORT](../ntdd8042/nc-ntdd8042-pi8042_synch_read_port.md) | The PI8042_SYNCH_READ_PORT-typed callback routine does a synchronized read from an i8042 port. I8042prt supplies this callback. |
| [PI8042_SYNCH_WRITE_PORT](../ntdd8042/nc-ntdd8042-pi8042_synch_write_port.md) | The PI8042_SYNCH_READ_PORT-typed callback routine does a synchronized write to an i8042 port. I8042prt supplies this routine. |
| [PSERVICE_CALLBACK_ROUTINE](../kbdmou/nc-kbdmou-pservice_callback_routine.md) | A function driver calls the class service callback in its ISR dispatch completion routine. The class service callback transfers input data from the input data buffer of a device to the class data queue. |



## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_GET_NUM_DEVICE_INPUT_BUFFERS IOCTL](../hidclass/ni-hidclass-ioctl_get_num_device_input_buffers.md) | The IOCTL_GET_NUM_DEVICE_INPUT_BUFFERS request obtains the size of the input report queue for a top-level collection. |
| [IOCTL_GET_PHYSICAL_DESCRIPTOR IOCTL](../hidclass/ni-hidclass-ioctl_get_physical_descriptor.md) | The IOCTL_GET_PHYSICAL_DESCRIPTOR request obtains the physical descriptor of a top-level collection. For a minidriver, this descriptor is the descriptor of the HIDClass device. |
| [IOCTL_HID_ACTIVATE_DEVICE IOCTL](../hidport/ni-hidport-ioctl_hid_activate_device.md) | The IOCTL_HID_ACTIVATE_DEVICE request activates a HIDClass device, which makes it ready for I/O operations. |
| [IOCTL_HID_DEACTIVATE_DEVICE IOCTL](../hidport/ni-hidport-ioctl_hid_deactivate_device.md) | The IOCTL_HID_DEACTIVATE_DEVICE request deactivates a HIDClass device, which causes it to stop operations and terminate all outstanding I/O requests. |
| [IOCTL_HID_DEVICERESET_NOTIFICATION IOCTL](../hidclass/ni-hidclass-ioctl_hid_devicereset_notification.md) | The IOCTL_HID_DEVICERESET_NOTIFICATION request is sent by the HID client driver to HID class driver to wait for a device-initiated reset event. |
| [IOCTL_HID_DISABLE_SECURE_READ IOCTL](../hidclass/ni-hidclass-ioctl_hid_disable_secure_read.md) | The IOCTL_HID_DISABLE_SECURE_READ request cancels an IOCTL_HID_ENABLE_SECURE_READ request for a HID collection. |
| [IOCTL_HID_ENABLE_SECURE_READ IOCTL](../hidclass/ni-hidclass-ioctl_hid_enable_secure_read.md) | The IOCTL_HID_ENABLE_SECURE_READ request enables a secure read for open files of a HID collection. |
| [IOCTL_HID_ENABLE_WAKE_ON_SX IOCTL](../hidclass/ni-hidclass-ioctl_hid_enable_wake_on_sx.md) | The IOCTL_HID_ENABLE_WAKE_ON_SX request is used to indicate the requirement for a device to be able to wake from system sleep. |
| [IOCTL_HID_FLUSH_QUEUE IOCTL](../hidclass/ni-hidclass-ioctl_hid_flush_queue.md) | The IOCTL_HID_FLUSH_QUEUE request dequeues all of the unparsed input reports from a top-level collection's input report queue. |
| [IOCTL_HID_GET_COLLECTION_DESCRIPTOR IOCTL](../hidclass/ni-hidclass-ioctl_hid_get_collection_descriptor.md) | The IOCTL_HID_GET_COLLECTION_DESCRIPTOR request obtains a top-level collection's preparsed data, which the HID class driver extracted from the physical device's report descriptor during device initialization. |
| [IOCTL_HID_GET_COLLECTION_INFORMATION IOCTL](../hidclass/ni-hidclass-ioctl_hid_get_collection_information.md) | The IOCTL_HID_GET_COLLECTION_INFORMATION request obtains a top-level collection's HID_COLLECTION_INFORMATION structure. |
| [IOCTL_HID_GET_DEVICE_ATTRIBUTES IOCTL](../hidport/ni-hidport-ioctl_hid_get_device_attributes.md) | The IOCTL_HID_GET_DEVICE_ATTRIBUTES request obtains a HIDClass device's attributes in a HID_DEVICE_ATTRIBUTES structure. |
| [IOCTL_HID_GET_DEVICE_DESCRIPTOR IOCTL](../hidport/ni-hidport-ioctl_hid_get_device_descriptor.md) | The IOCTL_HID_GET_DEVICE_DESCRIPTOR request obtains a HIDClass device's HID descriptor. |
| [IOCTL_HID_GET_DRIVER_CONFIG IOCTL](../hidclass/ni-hidclass-ioctl_hid_get_driver_config.md) | The IOCTL_HID_GET_DRIVER_CONFIG request retrieves the driver configuration. |
| [IOCTL_HID_GET_FEATURE IOCTL](../hidclass/ni-hidclass-ioctl_hid_get_feature.md) | The IOCTL_HID_GET_FEATURE request returns a feature report associated with a top-level collection. |
| [IOCTL_HID_GET_HARDWARE_ID IOCTL](../hidclass/ni-hidclass-ioctl_hid_get_hardware_id.md) | The IOCTL_HID_GET_HARDWARE_ID request obtains the Plug and Play hardware ID of a top-level collection. |
| [IOCTL_HID_GET_INDEXED_STRING IOCTL](../hidclass/ni-hidclass-ioctl_hid_get_indexed_string.md) | The IOCTL_HID_GET_INDEXED_STRING request obtains a specified embedded string from a top-level collection. |
| [IOCTL_HID_GET_INPUT_REPORT IOCTL](../hidclass/ni-hidclass-ioctl_hid_get_input_report.md) | The IOCTL_HID_GET_INPUT_REPORT request obtains an input report from a top-level collection. |
| [IOCTL_HID_GET_MANUFACTURER_STRING IOCTL](../hidclass/ni-hidclass-ioctl_hid_get_manufacturer_string.md) | The IOCTL_HID_GET_MANUFACTURER_STRING request obtains a top-level collection's embedded string that identifies the manufacturer of the device. |
| [IOCTL_HID_GET_MS_GENRE_DESCRIPTOR IOCTL](../hidclass/ni-hidclass-ioctl_hid_get_ms_genre_descriptor.md) | The IOCTL_HID_GET_MS_GENRE_DESCRIPTOR request is used for retrieving the genre descriptor for the device. |
| [IOCTL_HID_GET_POLL_FREQUENCY_MSEC IOCTL](../hidclass/ni-hidclass-ioctl_hid_get_poll_frequency_msec.md) | The IOCTL_HID_GET_POLL_FREQUENCY_MSEC request obtains the current polling frequency, in milliseconds, of a top-level collection. |
| [IOCTL_HID_GET_PRODUCT_STRING IOCTL](../hidclass/ni-hidclass-ioctl_hid_get_product_string.md) | The IOCTL_HID_GET_PRODUCT_STRING request obtains a top-level collection's embedded string that identifies the manufacturer's product. The retrieved string is a NULL-terminated wide character string in a human-readable format. |
| [IOCTL_HID_GET_REPORT_DESCRIPTOR IOCTL](../hidport/ni-hidport-ioctl_hid_get_report_descriptor.md) | The IOCTL_HID_GET_REPORT_DESCRIPTOR request obtains the report descriptor for a HIDClass device. |
| [IOCTL_HID_GET_SERIALNUMBER_STRING IOCTL](../hidclass/ni-hidclass-ioctl_hid_get_serialnumber_string.md) | The IOCTL_HID_GET_SERIALNUMBER_STRING request obtains a top-level collection's embedded string that identifies the device's serial number. |
| [IOCTL_HID_GET_STRING IOCTL](../hidport/ni-hidport-ioctl_hid_get_string.md) | The IOCTL_HID_GET_STRING request obtains a manufacturer ID, product ID, or serial number for a top-level collection. The retrieved string is a NULL-terminated wide character string in a human-readable format. |
| [IOCTL_HID_READ_REPORT IOCTL](../hidport/ni-hidport-ioctl_hid_read_report.md) | The IOCTL_HID_READ_REPORT request transfers an input report from a HIDClass device into the HID class driver's buffer. |
| [IOCTL_HID_SEND_IDLE_NOTIFICATION_REQUEST IOCTL](../hidport/ni-hidport-ioctl_hid_send_idle_notification_request.md) | The IOCTL_HID_SEND_IDLE_NOTIFICATION_REQUEST control code is the IOCTL of the idle notification request IRP that HIDClass sends to HID mini drivers, such as HIDUSB, to inform the bus driver that the device is now idle. |
| [IOCTL_HID_SET_DRIVER_CONFIG IOCTL](../hidclass/ni-hidclass-ioctl_hid_set_driver_config.md) | The IOCTL_HID_SET_DRIVER_CONFIG request sets the driver configuration. |
| [IOCTL_HID_SET_FEATURE IOCTL](../hidclass/ni-hidclass-ioctl_hid_set_feature.md) | The IOCTL_HID_SET_FEATURE request sends a feature report to a top-level collection. |
| [IOCTL_HID_SET_OUTPUT_REPORT IOCTL](../hidclass/ni-hidclass-ioctl_hid_set_output_report.md) | The IOCTL_HID_SET_OUTPUT_REPORT request sends an output report to a top-level collection. |
| [IOCTL_HID_SET_POLL_FREQUENCY_MSEC IOCTL](../hidclass/ni-hidclass-ioctl_hid_set_poll_frequency_msec.md) | The IOCTL_HID_SET_POLL_FREQUENCY_MSEC request sets the polling frequency, in milliseconds, for a top-level collection. |
| [IOCTL_HID_SET_S0_IDLE_TIMEOUT IOCTL](../hidclass/ni-hidclass-ioctl_hid_set_s0_idle_timeout.md) | The IOCTL_HID_SET_S0_IDLE_TIMEOUT request is used by a client to inform the HID class driver about the client's preferred idle timeout value. |
| [IOCTL_HID_WRITE_REPORT IOCTL](../hidport/ni-hidport-ioctl_hid_write_report.md) | The IOCTL_HID_WRITE_REPORT request sends a HID report to a HIDClass device. |
| [IOCTL_INTERNAL_I8042_CONTROLLER_WRITE_BUFFER IOCTL](../ntdd8042/ni-ntdd8042-ioctl_internal_i8042_controller_write_buffer.md) | The IOCTL_INTERNAL_I8042_CONTROLLER_WRITE_BUFFER request is not supported. |
| [IOCTL_INTERNAL_I8042_HOOK_KEYBOARD IOCTL](../ntdd8042/ni-ntdd8042-ioctl_internal_i8042_hook_keyboard.md) | The IOCTL_INTERNAL_I8042_HOOK_KEYBOARD request does the following |
| [IOCTL_INTERNAL_I8042_HOOK_MOUSE IOCTL](../ntdd8042/ni-ntdd8042-ioctl_internal_i8042_hook_mouse.md) | The IOCTL_INTERNAL_I8042_HOOK_MOUSE request adds an ISR callback routine to the I8042prt mouse ISR. |
| [IOCTL_INTERNAL_I8042_KEYBOARD_START_INFORMATION IOCTL](../ntdd8042/ni-ntdd8042-ioctl_internal_i8042_keyboard_start_information.md) | The IOCTL_INTERNAL_I8042_KEYBOARD_START_INFORMATION request passes a pointer to a keyboard interrupt object. |
| [IOCTL_INTERNAL_I8042_KEYBOARD_WRITE_BUFFER IOCTL](../ntdd8042/ni-ntdd8042-ioctl_internal_i8042_keyboard_write_buffer.md) | The IOCTL_INTERNAL_I8042_KEYBOARD_WRITE_BUFFER request writes data to the i8042 port controller to control operation of a keyboard device. |
| [IOCTL_INTERNAL_I8042_MOUSE_START_INFORMATION IOCTL](../ntdd8042/ni-ntdd8042-ioctl_internal_i8042_mouse_start_information.md) | The IOCTL_INTERNAL_I8042_MOUSE_START_INFORMATION request passes a pointer to a mouse interrupt object. |
| [IOCTL_INTERNAL_I8042_MOUSE_WRITE_BUFFER IOCTL](../ntdd8042/ni-ntdd8042-ioctl_internal_i8042_mouse_write_buffer.md) | The IOCTL_INTERNAL_I8042_MOUSE_WRITE_BUFFER request writes data to the i8042 port controller to control operation of a mouse device. |
| [IOCTL_INTERNAL_KEYBOARD_CONNECT IOCTL](../kbdmou/ni-kbdmou-ioctl_internal_keyboard_connect.md) | The IOCTL_INTERNAL_KEYBOARD_CONNECT request connects the Kbdclass service to the keyboard device. |
| [IOCTL_INTERNAL_KEYBOARD_DISCONNECT IOCTL](../kbdmou/ni-kbdmou-ioctl_internal_keyboard_disconnect.md) | The IOCTL_INTERNAL_KEYBOARD_DISCONNECT request is completed with a status of STATUS_NOT_IMPLEMENTED. Note that a Plug and Play keyboard can be added or removed by the Plug and Play manager. |
| [IOCTL_INTERNAL_MOUSE_CONNECT IOCTL](../kbdmou/ni-kbdmou-ioctl_internal_mouse_connect.md) | The IOCTL_INTERNAL_MOUSE_CONNECT request connects Mouclass service to a mouse device. |
| [IOCTL_INTERNAL_MOUSE_DISCONNECT IOCTL](../kbdmou/ni-kbdmou-ioctl_internal_mouse_disconnect.md) | The IOCTL_INTERNAL_MOUSE_DISCONNECT request is completed by Moufiltr with an error status of STATUS_NOT_IMPLEMENTED. |
| [IOCTL_SET_NUM_DEVICE_INPUT_BUFFERS IOCTL](../hidclass/ni-hidclass-ioctl_set_num_device_input_buffers.md) | The IOCTL_SET_NUM_DEVICE_INPUT_BUFFERS request sets the number of buffers for the input report queue of a top-level collection. |
| [IOCTL_UMDF_GET_PHYSICAL_DESCRIPTOR IOCTL](../hidport/ni-hidport-ioctl_umdf_get_physical_descriptor.md) | The IOCTL_UMDF_GET_PHYSICAL_DESCRIPTOR control code obtains the physical descriptor of a HIDClass device. |
| [IOCTL_UMDF_HID_GET_FEATURE IOCTL](../hidport/ni-hidport-ioctl_umdf_hid_get_feature.md) | The IOCTL_UMDF_HID_GET_FEATURE control code obtains a feature report from a HIDClass device. |
| [IOCTL_UMDF_HID_GET_INPUT_REPORT IOCTL](../hidport/ni-hidport-ioctl_umdf_hid_get_input_report.md) | The IOCTL_UMDF_HID_GET_INPUT_REPORT control code returns an input report from a HIDClass device. |
| [IOCTL_UMDF_HID_SET_FEATURE IOCTL](../hidport/ni-hidport-ioctl_umdf_hid_set_feature.md) | The IOCTL_UMDF_HID_GET_FEATURE control code sends a feature report to a HIDClass device. |
| [IOCTL_UMDF_HID_SET_OUTPUT_REPORT IOCTL](../hidport/ni-hidport-ioctl_umdf_hid_set_output_report.md) | The IOCTL_UMDF_HID_SET_OUTPUT_REPORT control code sends an output report to a top-level collection. |