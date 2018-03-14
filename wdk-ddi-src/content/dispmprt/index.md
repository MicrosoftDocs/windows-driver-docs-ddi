---
UID: NA:dispmprt
ms.assetid: c88cfcf2-97ac-371a-9a81-20a09d36eb77
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Dispmprt.h header



This header is used by Display. For more information, see
- [Display](../_display/index.md)

Dispmprt.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [DxgkInitialize function](nf-dispmprt-dxgkinitialize.md) | The DxgkInitialize function loads and initializes the DirectX graphics kernel subsystem (Dxgkrnl.sys). |
| [DxgkInitializeDisplayOnlyDriver function](nf-dispmprt-dxgkinitializedisplayonlydriver.md) | Loads and initializes the DirectX graphics kernel subsystem (Dxgkrnl.sys) for use by a kernel mode display-only driver (KMDOD). |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [DXGKCB_ACQUIRE_POST_DISPLAY_OWNERSHIP callback](nc-dispmprt-dxgkcb_acquire_post_display_ownership.md) | Called by a Windows Display Driver Model (WDDM) 1.2 or later display miniport driver to obtain the display information from the current power-on self-test (POST) display device or the previously running WDDM driver. |
| [DXGKCB_ACQUIRE_POST_DISPLAY_OWNERSHIP2 callback](nc-dispmprt-dxgkcb_acquire_post_display_ownership2.md) | Called by a display miniport driver to obtain the display information from the current power-on self-test (POST) display device or the previously running Windows Display Driver Model (WDDM) driver. |
| [DXGKCB_AGP_ALLOCATE_POOL callback](nc-dispmprt-dxgkcb_agp_allocate_pool.md) | The AgpAllocatePool function reserves, commits, and maps AGP memory. |
| [DXGKCB_AGP_FREE_POOL callback](nc-dispmprt-dxgkcb_agp_free_pool.md) | The AgpFreePool function frees AGP memory that was previously allocated by AgpAllocatePool. |
| [DXGKCB_AGP_SET_COMMAND callback](nc-dispmprt-dxgkcb_agp_set_command.md) | The AgpSetCommand function sets the AGP rate and specifies whether side band addressing and fast write transactions are enabled. |
| [DXGKCB_EVAL_ACPI_METHOD callback](nc-dispmprt-dxgkcb_eval_acpi_method.md) | The DxgkCbEvalAcpiMethod function evaluates a specified ACPI method on a display adapter or on a child device of a display adapter. |
| [DXGKCB_EXCLUDE_ADAPTER_ACCESS callback](nc-dispmprt-dxgkcb_exclude_adapter_access.md) | The DxgkCbExcludeAdapterAccess function prevents all access to the display adapter and calls a provided DxgkProtectedCallback callback routine while in this protected state. |
| [DXGKCB_GET_DEVICE_INFORMATION callback](nc-dispmprt-dxgkcb_get_device_information.md) | The DxgkCbGetDeviceInformation function gets information, including the registry path and a list of translated resources, about a specified display adapter. |
| [DXGKCB_INDICATE_CHILD_STATUS callback](nc-dispmprt-dxgkcb_indicate_child_status.md) | The DxgkCbIndicateChildStatus function records the current status of a specified child device of a display adapter. |
| [DXGKCB_IS_DEVICE_PRESENT callback](nc-dispmprt-dxgkcb_is_device_present.md) | The DxgkCbIsDevicePresent function determines whether a specified PCI device is present. |
| [DXGKCB_LOG_ETW_EVENT callback](nc-dispmprt-dxgkcb_log_etw_event.md) | The DxgkCbLogEtwEvent function logs an Event Tracing for Windows (ETW) event. |
| [DXGKCB_MAP_MEMORY callback](nc-dispmprt-dxgkcb_map_memory.md) | The DxgkCbMapMemory function maps a range of translated physical addresses (associated with a memory resource assigned to a display adapter) into system space or the virtual address space of a user-mode process. |
| [DXGKCB_MIRACAST_REPORT_CHUNK_INFO callback](nc-dispmprt-dxgkcb_miracast_report_chunk_info.md) | Called by the display miniport driver to report info about an encode chunk. |
| [DXGKCB_MIRACAST_SEND_MESSAGE callback](nc-dispmprt-dxgkcb_miracast_send_message.md) | Sends an asynchronous message to the user-mode display driver. |
| [DXGKCB_MIRACAST_SEND_MESSAGE_CALLBACK callback](nc-dispmprt-dxgkcb_miracast_send_message_callback.md) | Called in kernel mode when the message that was sent to the user-mode driver with a call to the DxgkCbMiracastSendMessage function has completed or has been canceled. |
| [DXGKCB_QUERY_SERVICES callback](nc-dispmprt-dxgkcb_query_services.md) | The DxgkCbQueryServices function returns an interface implemented by the display port driver. |
| [DXGKCB_QUEUE_DPC callback](nc-dispmprt-dxgkcb_queue_dpc.md) | The DxgkCbQueueDpc function queues a deferred procedure call (DPC) for execution at IRQL DISPATCH_LEVEL. |
| [DXGKCB_READ_DEVICE_SPACE callback](nc-dispmprt-dxgkcb_read_device_space.md) | The DxgkCbReadDeviceSpace function reads from a device configuration space or the expansion ROM of a display adapter. |
| [DXGKCB_SYNCHRONIZE_EXECUTION callback](nc-dispmprt-dxgkcb_synchronize_execution.md) | The DxgkCbSynchronizeExecution function synchronizes a specified function, implemented by the display miniport driver, with the display miniport driver's DxgkDdiInterruptRoutine function. |
| [DXGKCB_UNMAP_MEMORY callback](nc-dispmprt-dxgkcb_unmap_memory.md) | The DxgkCbUnmapMemory function unmaps a range of addresses previously mapped by DxgkCbMapMemory. |
| [DXGKCB_WRITE_DEVICE_SPACE callback](nc-dispmprt-dxgkcb_write_device_space.md) | The DxgkCbWriteDeviceSpace function writes to a device configuration space or the expansion ROM of a display adapter. |
| [DXGKDDI_ADD_DEVICE callback](nc-dispmprt-dxgkddi_add_device.md) | The DxgkDdiAddDevice function creates a context block for a display adapter and returns a handle that represents the display adapter. |
| [DXGKDDI_CONTROL_ETW_LOGGING callback](nc-dispmprt-dxgkddi_control_etw_logging.md) | The DxgkDdiControlEtwLogging function enables or disables Event Tracing for Windows (ETW) event logging. |
| [DXGKDDI_DISPATCH_IO_REQUEST callback](nc-dispmprt-dxgkddi_dispatch_io_request.md) | The DxgkDdiDispatchIoRequest function handles I/O control (IOCTL) requests. |
| [DXGKDDI_DPC_ROUTINE callback](nc-dispmprt-dxgkddi_dpc_routine.md) | The DxgkDdiDpcRoutine function is called back at IRQL DISPATCH_LEVEL after the display miniport driver calls DxgkCbQueueDpc. |
| [DXGKDDI_EXCHANGEPRESTARTINFO callback](nc-dispmprt-dxgkddi_exchangeprestartinfo.md) | Allows very simple data to be exchanged between the OS and driver which may be required prior to DxgkDdiStartDevice device being called and therefore cannot be queried through normal caps or adapter info DDIs. |
| [DXGKDDI_GET_CHILD_CONTAINER_ID callback](nc-dispmprt-dxgkddi_get_child_container_id.md) | Queries the container ID for the specified target. Implemented by Windows Display Driver Model (WDDM) 1.2 and later display miniport drivers. |
| [DXGKDDI_I2C_RECEIVE_DATA_FROM_DISPLAY callback](nc-dispmprt-dxgkddi_i2c_receive_data_from_display.md) | The DxgkDdiI2CReceiveDataFromDisplay returns data received from an I2C device in a monitor. |
| [DXGKDDI_I2C_TRANSMIT_DATA_TO_DISPLAY callback](nc-dispmprt-dxgkddi_i2c_transmit_data_to_display.md) | The DxgkDdiI2CTransmitDataToDisplay function transmits data to an I2C device in a monitor. |
| [DXGKDDI_INTERRUPT_ROUTINE callback](nc-dispmprt-dxgkddi_interrupt_routine.md) | The DxgkDdiInterruptRoutine function handles interrupts generated by a display adapter. |
| [DXGKDDI_LINK_DEVICE callback](nc-dispmprt-dxgkddi_link_device.md) | The optional DxgkDdiLinkDevice function queries the display miniport driver for information on the linked adapter configuration. |
| [DXGKDDI_MIRACAST_CREATE_CONTEXT callback](nc-dispmprt-dxgkddi_miracast_create_context.md) | Creates a kernel-mode context for a Miracast device. |
| [DXGKDDI_MIRACAST_DESTROY_CONTEXT callback](nc-dispmprt-dxgkddi_miracast_destroy_context.md) | Destroys an instance of a Miracast device. |
| [DXGKDDI_MIRACAST_HANDLE_IO_CONTROL callback](nc-dispmprt-dxgkddi_miracast_handle_io_control.md) | Called by the operating system to request that the display miniport driver process a synchronous I/O control request in response to a user-mode display driver call to the MiracastIoControl function. |
| [DXGKDDI_MIRACAST_QUERY_CAPS callback](nc-dispmprt-dxgkddi_miracast_query_caps.md) | Queries the Miracast capabilities of the current display adapter. |
| [DXGKDDI_NOTIFY_ACPI_EVENT callback](nc-dispmprt-dxgkddi_notify_acpi_event.md) | Notifies the display miniport driver about certain ACPI events. |
| [DXGKDDI_NOTIFY_SURPRISE_REMOVAL callback](nc-dispmprt-dxgkddi_notify_surprise_removal.md) | Called by the operating system after a user disconnected an external display device without notifying the system.Can optionally be implemented by Windows Display Driver Model (WDDM) 1.2 and later display miniport drivers. |
| [DXGKDDI_OPM_CONFIGURE_PROTECTED_OUTPUT callback](nc-dispmprt-dxgkddi_opm_configure_protected_output.md) | The DxgkDdiOPMConfigureProtectedOutput function configures the given protected output object. |
| [DXGKDDI_OPM_CREATE_PROTECTED_OUTPUT callback](nc-dispmprt-dxgkddi_opm_create_protected_output.md) | The DxgkDdiOPMCreateProtectedOutput function creates a new protected output object with Certified Output Protection Protocol (COPP) or OPM semantics. |
| [DXGKDDI_OPM_DESTROY_PROTECTED_OUTPUT callback](nc-dispmprt-dxgkddi_opm_destroy_protected_output.md) | The DxgkDdiOPMDestroyProtectedOutput function destroys the given protected output object. |
| [DXGKDDI_OPM_GET_CERTIFICATE callback](nc-dispmprt-dxgkddi_opm_get_certificate.md) | The DxgkDdiOPMGetCertificate function retrieves a certificate of the given type and size. |
| [DXGKDDI_OPM_GET_CERTIFICATE_SIZE callback](nc-dispmprt-dxgkddi_opm_get_certificate_size.md) | The DxgkDdiOPMGetCertificateSize function retrieves the size of a certificate of the given type. |
| [DXGKDDI_OPM_GET_COPP_COMPATIBLE_INFORMATION callback](nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md) | The DxgkDdiOPMGetCOPPCompatibleInformation function retrieves information that is compatible with the Certified Output Protection Protocol (COPP) from the given protected output object. |
| [DXGKDDI_OPM_GET_INFORMATION callback](nc-dispmprt-dxgkddi_opm_get_information.md) | The DxgkDdiOPMGetInformation function retrieves information from the given protected output object. |
| [DXGKDDI_OPM_GET_RANDOM_NUMBER callback](nc-dispmprt-dxgkddi_opm_get_random_number.md) | The DxgkDdiOPMGetRandomNumber function retrieves the given protected output object's 128-bit cryptographically secure random number. |
| [DXGKDDI_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS callback](nc-dispmprt-dxgkddi_opm_set_signing_key_and_sequence_numbers.md) | The DxgkDdiOPMSetSigningKeyAndSequenceNumbers function sets the given protected output object's signing key and two sequence numbers. |
| [DXGKDDI_PROTECTED_CALLBACK callback](nc-dispmprt-dxgkddi_protected_callback.md) | The DxgkProtectedCallback callback routine is implemented by the display miniport driver and is called by DxgkCbExcludeAdapterAccess during a protected state when all access to the display adapter is prevented. |
| [DXGKDDI_QUERY_CHILD_RELATIONS callback](nc-dispmprt-dxgkddi_query_child_relations.md) | The DxgkDdiQueryChildRelations function enumerates the child devices of a display adapter. |
| [DXGKDDI_QUERY_CHILD_STATUS callback](nc-dispmprt-dxgkddi_query_child_status.md) | The DxgkDdiQueryChildStatus function returns the status of an individual child device of a display adapter. |
| [DXGKDDI_QUERY_DEVICE_DESCRIPTOR callback](nc-dispmprt-dxgkddi_query_device_descriptor.md) | The DxgkDdiQueryDeviceDescriptor function returns a descriptor for a child device of a display adapter or for an external device (typically a monitor) connected to a child device of a display adapter. |
| [DXGKDDI_QUERY_INTERFACE callback](nc-dispmprt-dxgkddi_query_interface.md) | The DxgkDdiQueryInterface function returns a functional interface that is implemented by the display miniport driver. |
| [DXGKDDI_REMOVE_DEVICE callback](nc-dispmprt-dxgkddi_remove_device.md) | The DxgkDdiRemoveDevice function frees any resources allocated during DxgkDdiAddDevice. |
| [DXGKDDI_RESET_DEVICE callback](nc-dispmprt-dxgkddi_reset_device.md) | The DxgkDdiResetDevice function sets a display adapter to VGA character mode (80 x 50). |
| [DXGKDDI_SETTARGETADJUSTEDCOLORIMETRY callback](nc-dispmprt-dxgkddi_settargetadjustedcolorimetry.md) | Reports the colorimetry values selected by the OS for a target. |
| [DXGKDDI_SET_POWER_STATE callback](nc-dispmprt-dxgkddi_set_power_state.md) | The DxgkDdiSetPowerState function sets the power state of a display adapter or a child device of a display adapter. |
| [DXGKDDI_START_DEVICE callback](nc-dispmprt-dxgkddi_start_device.md) | The DxgkDdiStartDevice function prepares a display adapter to receive I/O requests. |
| [DXGKDDI_STOP_DEVICE callback](nc-dispmprt-dxgkddi_stop_device.md) | The DxgkDdiStopDevice function resets a display adapter and frees resources allocated during DxgkDdiStartDevice. |
| [DXGKDDI_STOP_DEVICE_AND_RELEASE_POST_DISPLAY_OWNERSHIP callback](nc-dispmprt-dxgkddi_stop_device_and_release_post_display_ownership.md) | Called by the operating system to request the display miniport driver to reset the display device and to release ownership of the current power-on self-test (POST) device. |
| [DXGKDDI_SYSTEM_DISPLAY_ENABLE callback](nc-dispmprt-dxgkddi_system_display_enable.md) | Called by the operating system to request the display miniport driver to reset the current display device to a specified state. |
| [DXGKDDI_SYSTEM_DISPLAY_WRITE callback](nc-dispmprt-dxgkddi_system_display_write.md) | Called by the operating system to request the display miniport driver to write an image block to the display device. |
| [DXGKDDI_UNLOAD callback](nc-dispmprt-dxgkddi_unload.md) | The DxgkDdiUnload function frees any resources allocated during execution of the display miniport driver's DriverEntry function. |
| [DXGK_BRIGHTNESS_GET callback](nc-dispmprt-dxgk_brightness_get.md) | The DxgkDdiGetBrightness function retrieves the currently active brightness level of an integrated display panel. |
| [DXGK_BRIGHTNESS_GET_BACKLIGHT_REDUCTION callback](nc-dispmprt-dxgk_brightness_get_backlight_reduction.md) | Retrieves the current level of backlight reduction that is applied to the integrated display panel. |
| [DXGK_BRIGHTNESS_GET_CAPS callback](nc-dispmprt-dxgk_brightness_get_caps.md) | Retrieves brightness control capabilities of an integrated display panel. |
| [DXGK_BRIGHTNESS_GET_POSSIBLE callback](nc-dispmprt-dxgk_brightness_get_possible.md) | The DxgkDdiGetPossibleBrightness function retrieves the brightness levels that an integrated display panel supports. |
| [DXGK_BRIGHTNESS_SET callback](nc-dispmprt-dxgk_brightness_set.md) | The DxgkDdiSetBrightness function sets a new brightness level. |
| [DXGK_BRIGHTNESS_SET_BACKLIGHT_OPTIMIZATION callback](nc-dispmprt-dxgk_brightness_set_backlight_optimization.md) | Called by the Microsoft DirectX graphics kernel subsystem to set the level of optimization that the display miniport driver uses to control the brightness of an integrated display panel. |
| [DXGK_BRIGHTNESS_SET_STATE callback](nc-dispmprt-dxgk_brightness_set_state.md) | Enables smooth brightness control on an integrated display panel. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [DXGK_BRIGHTNESS_INTERFACE structure](ns-dispmprt-dxgk_brightness_interface.md) | The DXGK_BRIGHTNESS_INTERFACE structure contains pointers to functions in the Panel Brightness Control Interface, which is implemented by the display miniport driver. |
| [DXGK_BRIGHTNESS_INTERFACE_2 structure](ns-dispmprt-dxgk_brightness_interface_2.md) | Contains pointers to functions in the Panel Brightness Control Interface Version 2. Used by Windows Display Driver Model (WDDM) 1.2 and later display miniport drivers that support adaptive and smooth brightness control. |
| [_DRIVER_INITIALIZATION_DATA structure](ns-dispmprt-_driver_initialization_data.md) | The DRIVER_INITIALIZATION_DATA structure contains pointers to functions implemented by the display miniport driver. |
| [_DXGKRNL_INTERFACE structure](ns-dispmprt-_dxgkrnl_interface.md) | The DXGKRNL_INTERFACE structure contains a handle to a display adapter and a set of function pointers. |
| [_DXGK_AGP_INTERFACE structure](ns-dispmprt-_dxgk_agp_interface.md) | The DXGK_AGP_INTERFACE structure contains pointers to functions in the AGP interface, which is implemented by the display port driver. |
| [_DXGK_CHILD_CAPABILITIES structure](ns-dispmprt-_dxgk_child_capabilities.md) | The DXGK_CHILD_CAPABILITIES structure contains information about the capabilities of an individual child device of a display adapter. |
| [_DXGK_CHILD_CONTAINER_ID structure](ns-dispmprt-_dxgk_child_container_id.md) | Contains the container ID for a child device that is connected to a display adapter. |
| [_DXGK_CHILD_DESCRIPTOR structure](ns-dispmprt-_dxgk_child_descriptor.md) | The DXGK_CHILD_DESCRIPTOR structure holds identification and capability information for an individual child device of the display adapter. |
| [_DXGK_CHILD_STATUS structure](ns-dispmprt-_dxgk_child_status.md) | The DXGK_CHILD_STATUS structure contains members that indicate the status of a child device of the display adapter. |
| [_DXGK_DEBUG_REPORT_INTERFACE structure](ns-dispmprt-_dxgk_debug_report_interface.md) | The DXGK_DEBUG_REPORT_INTERFACE structure contains pointers to functions in the Debug Report interface, which is implemented by the display port driver. |
| [_DXGK_DEVICE_DESCRIPTOR structure](ns-dispmprt-_dxgk_device_descriptor.md) | The DXGK_DEVICE_DESCRIPTOR structure is used by the display port driver to request that the display miniport driver return all or a portion of a monitor's Extended Display Identification Data (EDID). |
| [_DXGK_DEVICE_INFO structure](ns-dispmprt-_dxgk_device_info.md) | The DXGK_DEVICE_INFO structure holds information that describes a display adapter. |
| [_DXGK_DISPLAY_OWNERSHIP_FLAGS structure](ns-dispmprt-_dxgk_display_ownership_flags.md) | Structure filled in by OS upon successful completion of the DxgkCbAcquirePostDisplayOwnership2 callback to provide information about the display state a driver is inheriting. |
| [_DXGK_FIRMWARE_TABLE_INTERFACE structure](ns-dispmprt-_dxgk_firmware_table_interface.md) | Contains functions that user-mode display drivers can use to read and enumerate the system firmware table. These functions are supplied by the Microsoft DirectX graphics kernel subsystem and can be called by WDDM 1.2 and later user-mode display drivers. |
| [_DXGK_GENERIC_DESCRIPTOR structure](ns-dispmprt-_dxgk_generic_descriptor.md) | The DXGK_GENERIC_DESCRIPTOR structure contains descriptive information about a child device of the display adapter. |
| [_DXGK_I2C_INTERFACE structure](ns-dispmprt-_dxgk_i2c_interface.md) | The DXGK_I2C_INTERFACE structure contains pointers to functions in the I2C interface, which is implemented by the display miniport driver. |
| [_DXGK_INTEGRATED_DISPLAY_CHILD structure](ns-dispmprt-_dxgk_integrated_display_child.md) | Gives information about the connected integrated display. |
| [_DXGK_MIRACAST_CAPS structure](ns-dispmprt-_dxgk_miracast_caps.md) | Used by a display miniport driver to identify capabilities of a Miracast device. |
| [_DXGK_MIRACAST_DISPLAY_CALLBACKS structure](ns-dispmprt-_dxgk_miracast_display_callbacks.md) | Contains pointers to functions in the Wireless display (Miracast) display callback interface that the display miniport driver can call to send messages and report encode chunk info. |
| [_DXGK_MIRACAST_INTERFACE structure](ns-dispmprt-_dxgk_miracast_interface.md) | Contains pointers to functions in the Wireless display (Miracast) interface that the display miniport driver implements to create, destroy, query, and control Miracast device resources. |
| [_DXGK_OPM_INTERFACE structure](ns-dispmprt-_dxgk_opm_interface.md) | The DXGK_OPM_INTERFACE structure contains pointers to functions in the Output Protection Manager (OPM) Interface, which is implemented by the display miniport driver. |
| [_DXGK_OPM_INTERFACE_3 structure](ns-dispmprt-_dxgk_opm_interface_3.md) | The DXGK_OPM_INTERFACE_3 structure contains pointers to functions in the Output Protection Manager (OPM) Interface, which is implemented by the display miniport driver. |
| [_DXGK_PRE_START_INFO structure](ns-dispmprt-_dxgk_pre_start_info.md) | Structure to allow very simple data to be exchanged between the OS and driver which may be required prior to start device being called and therefore cannot be queried through normal caps or adapter info DDIs. |
| [_DXGK_SPB_INTERFACE structure](ns-dispmprt-_dxgk_spb_interface.md) | Contains pointers to functions in the Simple Peripheral Bus (SPB) Interface that the Windows Display Driver Model (WDDM) 1.2 and later display miniport driver can call to inspect and alter SPB resources. |
| [_DXGK_START_INFO structure](ns-dispmprt-_dxgk_start_info.md) | The DXGK_START_INFO structure holds information that is needed by the display miniport driver's DxgkDdiStartDevice function. |
| [_DXGK_TIMED_OPERATION structure](ns-dispmprt-_dxgk_timed_operation.md) | The DXGK_TIMED_OPERATION structure describes a timed operation, which is used in the Timed Operation Interface. |
| [_DXGK_TIMED_OPERATION_INTERFACE structure](ns-dispmprt-_dxgk_timed_operation_interface.md) | The DXGK_TIMED_OPERATION_INTERFACE structure contains pointers to functions in the Timed Operation Interface, which is implemented by the display port driver. |
| [_DXGK_VIDEO_OUTPUT_CAPABILITIES structure](ns-dispmprt-_dxgk_video_output_capabilities.md) | The DXGK_VIDEO_OUTPUT_CAPABILITIES structure contains information about the capabilities of a video output on a display adapter. |
| [_EMULATOR_ACCESS_ENTRY structure](ns-dispmprt-_emulator_access_entry.md) | The EMULATOR_ACCESS_ENTRY structure specifies an element in the EmulatorAccessEntries array set up in the VIDEO_PORT_CONFIG_INFO structure by drivers of VGA-compatible (SVGA) adapters on x86-based NT-based operating system platforms. |
| [_KMDDOD_INITIALIZATION_DATA structure](ns-dispmprt-_kmddod_initialization_data.md) | Contains pointers to functions implemented by a kernel mode display-only driver (KMDOD). The KMDOD's DriverEntry function provides the Microsoft DirectX graphics kernel subsystem with entry points by filling in the members of this structure. |
| [_LINKED_DEVICE structure](ns-dispmprt-_linked_device.md) | The LINKED_DEVICE structure holds information that describes a linked display adapter configuration. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [DOCKING_STATE enumeration](ne-dispmprt-docking_state.md) | The DOCKING_STATE enumeration is used to describe the state of a portable computer that can be attached to a docking station. |
| [DXGK_SERVICES enumeration](ne-dispmprt-dxgk_services.md) | The DXGK_SERVICES enumeration indicates the type of interface being requested by a call to the DxgkCbQueryServices function. |
| [_DXGK_CHILD_DEVICE_TYPE enumeration](ne-dispmprt-_dxgk_child_device_type.md) | The DXGK_CHILD_DEVICE_TYPE enumeration is used to indicate the type of a child device of the display adapter. |
| [_DXGK_CHILD_STATUS_TYPE enumeration](ne-dispmprt-_dxgk_child_status_type.md) | The DXGK_CHILD_STATUS_TYPE enumeration indicates the type of status being requested or reported for a child device of the display adapter. |
| [_DXGK_EVENT_TYPE enumeration](ne-dispmprt-_dxgk_event_type.md) | The DXGK_EVENT_TYPE enumeration indicates the event type in a call to the display miniport driver's DxgkDdiNotifyAcpiEvent function. |
| [_DXGK_FRAMEBUFFER_STATE enumeration](ne-dispmprt-_dxgk_framebuffer_state.md) | The frame buffer state is provided to the driver in order that the driver can infer details of the display configuration based on knowledge of how firmware and the driver will set a particular resolution even though only basic information is made directly available by the OS to the driver. |
| [_DXGK_SURPRISE_REMOVAL_TYPE enumeration](ne-dispmprt-_dxgk_surprise_removal_type.md) | Indicates the type of surprise removal event when an external display device is disconnected from the system. |
