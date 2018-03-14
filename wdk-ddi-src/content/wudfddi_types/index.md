---
UID: NA:wudfddi_types
ms.assetid: 4b61f22a-ca30-3fe9-9635-a2872e82d5dd
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Wudfddi_Types.h header



This header is used by Windows Driver Framework. For more information, see
- [Windows Driver Framework](../_wdf/index.md)

Wudfddi_Types.h contain these programming interfaces:


## Structures

| Title   | Description   |
| ---- |:---- |
| [UMDF_VERSION_DATA structure](ns-wudfddi_types-umdf_version_data.md) | The UMDF_VERSION_DATA structure describes a version of the framework. |
| [_WDFMEMORY_OFFSET structure](ns-wudfddi_types-_wdfmemory_offset.md) | The WDFMEMORY_OFFSET structure describes the location and size of information that is accessed within a memory block. |
| [_WDF_PROPERTY_STORE_ROOT structure](ns-wudfddi_types-_wdf_property_store_root.md) | The WDF_PROPERTY_STORE_ROOT structure contains information that identifies a UMDF property store. |
| [_WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS structure](ns-wudfddi_types-_wudf_device_power_policy_idle_settings.md) | The WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS structure contains driver-supplied information that the framework uses when a device is idle and the system is in the system working state (S0). |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_WDF_CALLBACK_CONSTRAINT enumeration](ne-wudfddi_types-_wdf_callback_constraint.md) | WDF_CALLBACK_CONSTRAINT enumeration |
| [_WDF_DEVICE_HWACCESS_TARGET_SIZE enumeration](ne-wudfddi_types-_wdf_device_hwaccess_target_size.md) | The WDF_DEVICE_HWACCESS_TARGET_SIZE enumeration is used internally by the framework. Do not use. |
| [_WDF_DEVICE_HWACCESS_TARGET_TYPE enumeration](ne-wudfddi_types-_wdf_device_hwaccess_target_type.md) | The WDF_DEVICE_HWACCESS_TARGET_TYPE enumeration is used internally by the framework. Do not use. |
| [_WDF_DEVICE_IO_BUFFER_RETRIEVAL enumeration](ne-wudfddi_types-_wdf_device_io_buffer_retrieval.md) | The WDF_DEVICE_IO_BUFFER_RETRIEVAL enumeration is used to specify when UMDF makes an I/O request's buffers available to the driver. |
| [_WDF_DEVICE_IO_TYPE enumeration](ne-wudfddi_types-_wdf_device_io_type.md) | The WDF_DEVICE_IO_TYPE enumeration is used to specify a method for accessing data buffers. |
| [_WDF_EVENT_TYPE enumeration](ne-wudfddi_types-_wdf_event_type.md) | The WDF_EVENT_TYPE enumeration specifies. |
| [_WDF_FILE_INFORMATION_CLASS enumeration](ne-wudfddi_types-_wdf_file_information_class.md) | The WDF_FILE_INFORMATION_CLASS enumeration identifies the types of file information that a driver can obtain or set. |
| [_WDF_IO_QUEUE_DISPATCH_TYPE enumeration](ne-wudfddi_types-_wdf_io_queue_dispatch_type.md) | The WDF_IO_QUEUE_DISPATCH_TYPE enumeration contains values that identify how a driver must receive requests from an I/O queue. |
| [_WDF_IO_QUEUE_STATE enumeration](ne-wudfddi_types-_wdf_io_queue_state.md) | The WDF_IO_QUEUE_STATE enumeration contains values that identify the state of an I/O queue. |
| [_WDF_IO_TARGET_SENT_IO_ACTION enumeration](ne-wudfddi_types-_wdf_io_target_sent_io_action.md) | The WDF_IO_TARGET_SENT_IO_ACTION enumeration identifies the actions that the framework can take when a driver calls IWDFIoTargetStateManagement |
| [_WDF_IO_TARGET_STATE enumeration](ne-wudfddi_types-_wdf_io_target_state.md) | The WDF_IO_TARGET_STATE enumeration specifies the states that an I/O target can be in. |
| [_WDF_KPROCESSOR_MODE enumeration](ne-wudfddi_types-_wdf_kprocessor_mode.md) | The WDF_KPROCESSOR_MODE enumeration type identifies the processor modes in which a thread can execute. |
| [_WDF_PNP_CAPABILITY enumeration](ne-wudfddi_types-_wdf_pnp_capability.md) | The WDF_PNP_CAPABILITY enumeration contains values that identify Plug and Play (PnP) capabilities for a device. |
| [_WDF_PNP_STATE enumeration](ne-wudfddi_types-_wdf_pnp_state.md) | The WDF_PNP_STATE enumeration contains values that identify the status of Plug and Play (PnP) for a device. |
| [_WDF_POWER_DEVICE_STATE enumeration](ne-wudfddi_types-_wdf_power_device_state.md) | The WDF_POWER_DEVICE_STATE enumeration contains values that identify the power state that a device might support. |
| [_WDF_POWER_POLICY_IDLE_TIMEOUT_CONSTANTS enumeration](ne-wudfddi_types-_wdf_power_policy_idle_timeout_constants.md) | The WDF_POWER_POLICY_IDLE_TIMEOUT_CONSTANTS enumeration is reserved for internal use. |
| [_WDF_POWER_POLICY_S0_IDLE_CAPABILITIES enumeration](ne-wudfddi_types-_wdf_power_policy_s0_idle_capabilities.md) | The WDF_POWER_POLICY_S0_IDLE_CAPABILITIES enumeration identifies the capabilities that a device can support when it enters a low-power state while it is idling. |
| [_WDF_POWER_POLICY_S0_IDLE_USER_CONTROL enumeration](ne-wudfddi_types-_wdf_power_policy_s0_idle_user_control.md) | The WDF_POWER_POLICY_S0_IDLE_USER_CONTROL enumeration identifies whether a user can control a device's behavior when the device is idle and the system is in its working (S0) state. |
| [_WDF_POWER_POLICY_SX_WAKE_USER_CONTROL enumeration](ne-wudfddi_types-_wdf_power_policy_sx_wake_user_control.md) | The WDF_POWER_POLICY_SX_WAKE_USER_CONTROL enumeration identifies whether a user can control a device's ability to wake the system from a low system power state. |
| [_WDF_PROPERTY_STORE_DISPOSITION enumeration](ne-wudfddi_types-_wdf_property_store_disposition.md) | The WDF_PROPERTY_STORE_DISPOSITION enumeration contains values that indicate whether a registry value was created or already existed when a driver obtained a property store interface. |
| [_WDF_PROPERTY_STORE_RETRIEVE_FLAGS enumeration](ne-wudfddi_types-_wdf_property_store_retrieve_flags.md) | The WDF_PROPERTY_STORE_RETRIEVE_FLAGS enumeration contains values that indicate whether UMDF should create a registry key if the key does not already exist. |
| [_WDF_PROPERTY_STORE_ROOT_CLASS enumeration](ne-wudfddi_types-_wdf_property_store_root_class.md) | The WDF_PROPERTY_STORE_ROOT_CLASS enumeration identifies the registry keys that UMDF property stores represent. |
| [_WDF_REQUEST_SEND_OPTIONS_FLAGS enumeration](ne-wudfddi_types-_wdf_request_send_options_flags.md) | The WDF_REQUEST_SEND_OPTIONS_FLAGS enumeration type defines flags that a driver can specify when it calls IWDFIoRequest |
| [_WDF_REQUEST_STOP_ACTION_FLAGS enumeration](ne-wudfddi_types-_wdf_request_stop_action_flags.md) | The WDF_REQUEST_STOP_ACTION_FLAGS enumeration contains values that identify the state of a stop action request in a call to the driver's IQueueCallbackIoStop |
| [_WDF_REQUEST_TYPE enumeration](ne-wudfddi_types-_wdf_request_type.md) | The WDF_REQUEST_TYPE enumeration identifies the types of I/O requests that a UMDF request object can represent. |
| [_WDF_TRI_STATE enumeration](ne-wudfddi_types-_wdf_tri_state.md) | The WDF_TRI_STATE enumeration type defines three values that the framework uses for some structure members and function parameters. |
