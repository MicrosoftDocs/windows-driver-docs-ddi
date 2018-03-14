---
UID: NA:wdfusb
ms.assetid: 3e6fc683-b610-3c72-8797-368ee1f97630
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Wdfusb.h header



This header is used by Windows Driver Framework. For more information, see
- [Windows Driver Framework](../_wdf/index.md)

Wdfusb.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [WDF_USB_CONTINUOUS_READER_CONFIG_INIT function](nf-wdfusb-wdf_usb_continuous_reader_config_init.md) | The WDF_USB_CONTINUOUS_READER_CONFIG_INIT function initializes a WDF_USB_CONTINUOUS_READER_CONFIG structure. |
| [WDF_USB_CONTROL_SETUP_PACKET_INIT function](nf-wdfusb-wdf_usb_control_setup_packet_init.md) | The WDF_USB_CONTROL_SETUP_PACKET_INIT function initializes a WDF_USB_CONTROL_SETUP_PACKET structure for a standard USB control transfer. |
| [WDF_USB_CONTROL_SETUP_PACKET_INIT_CLASS function](nf-wdfusb-wdf_usb_control_setup_packet_init_class.md) | The WDF_USB_CONTROL_SETUP_PACKET_INIT_CLASS function initializes a WDF_USB_CONTROL_SETUP_PACKET structure for a device class-specific USB control transfer. |
| [WDF_USB_CONTROL_SETUP_PACKET_INIT_FEATURE function](nf-wdfusb-wdf_usb_control_setup_packet_init_feature.md) | The WDF_USB_CONTROL_SETUP_PACKET_INIT_FEATURE function initializes a WDF_USB_CONTROL_SETUP_PACKET structure for a USB control transfer that sets or clears a device feature. |
| [WDF_USB_CONTROL_SETUP_PACKET_INIT_GET_STATUS function](nf-wdfusb-wdf_usb_control_setup_packet_init_get_status.md) | The WDF_USB_CONTROL_SETUP_PACKET_INIT_GET_STATUS function initializes a WDF_USB_CONTROL_SETUP_PACKET structure for a USB control transfer that obtains device status. |
| [WDF_USB_CONTROL_SETUP_PACKET_INIT_VENDOR function](nf-wdfusb-wdf_usb_control_setup_packet_init_vendor.md) | The WDF_USB_CONTROL_SETUP_PACKET_INIT_VENDOR function initializes a WDF_USB_CONTROL_SETUP_PACKET structure for a vendor-specific USB control transfer. |
| [WDF_USB_DEVICE_CREATE_CONFIG_INIT function](nf-wdfusb-wdf_usb_device_create_config_init.md) | The WDF_USB_DEVICE_CREATE_CONFIG_INIT function initializes a WDF_USB_DEVICE_CREATE_CONFIG structure. |
| [WDF_USB_DEVICE_INFORMATION_INIT function](nf-wdfusb-wdf_usb_device_information_init.md) | The WDF_USB_DEVICE_INFORMATION_INIT function initializes a driver's WDF_USB_DEVICE_INFORMATION structure. |
| [WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_DECONFIG function](nf-wdfusb-wdf_usb_device_select_config_params_init_deconfig.md) | The WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_DECONFIG function initializes a WDF_USB_DEVICE_SELECT_CONFIG_PARAMS structure so that a driver can deconfigure a USB device. |
| [WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_INTERFACES_DESCRIPTORS function](nf-wdfusb-wdf_usb_device_select_config_params_init_interfaces_descriptors.md) | The WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_INTERFACES_DESCRIPTORS function initializes a WDF_USB_DEVICE_SELECT_CONFIG_PARAMS structure so that a driver can specify a configuration by using USB descriptors. |
| [WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES function](nf-wdfusb-wdf_usb_device_select_config_params_init_multiple_interfaces.md) | The WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES function initializes a WDF_USB_DEVICE_SELECT_CONFIG_PARAMS structure so that a driver can configure a device to use multiple interfaces. |
| [WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_SINGLE_INTERFACE function](nf-wdfusb-wdf_usb_device_select_config_params_init_single_interface.md) | The WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_SINGLE_INTERFACE function initializes a WDF_USB_DEVICE_SELECT_CONFIG_PARAMS structure so that a driver can configure a device to use a single, specified interface. |
| [WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_URB function](nf-wdfusb-wdf_usb_device_select_config_params_init_urb.md) | The WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_URB function initializes a WDF_USB_DEVICE_SELECT_CONFIG_PARAMS structure so that a driver can specify a configuration by using a URB. |
| [WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_DESCRIPTOR function](nf-wdfusb-wdf_usb_interface_select_setting_params_init_descriptor.md) | The WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_DESCRIPTOR function initializes a WDF_USB_INTERFACE_SELECT_SETTING_PARAMS structure so that a driver can select a USB interface by specifying an interface descriptor. |
| [WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_SETTING function](nf-wdfusb-wdf_usb_interface_select_setting_params_init_setting.md) | The WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_SETTING function initializes a WDF_USB_INTERFACE_SELECT_SETTING_PARAMS structure so that a driver can select a USB interface by specifying a handle to an interface object and an alternate setting for the interface. |
| [WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB function](nf-wdfusb-wdf_usb_interface_select_setting_params_init_urb.md) | The WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB function initializes a WDF_USB_INTERFACE_SELECT_SETTING_PARAMS structure so that a driver can select a USB interface by specifying a URB. |
| [WDF_USB_PIPE_DIRECTION_IN function](nf-wdfusb-wdf_usb_pipe_direction_in.md) | The WDF_USB_PIPE_DIRECTION_IN function determines whether a specified USB endpoint is an input endpoint. |
| [WDF_USB_PIPE_DIRECTION_OUT function](nf-wdfusb-wdf_usb_pipe_direction_out.md) | The WDF_USB_PIPE_DIRECTION_OUT function determines whether a specified USB endpoint is an output endpoint. |
| [WDF_USB_PIPE_INFORMATION_INIT function](nf-wdfusb-wdf_usb_pipe_information_init.md) | The WDF_USB_PIPE_INFORMATION_INIT function initializes a WDF_USB_PIPE_INFORMATION structure. |
| [WdfUsbInterfaceGetConfiguredPipe function](nf-wdfusb-wdfusbinterfacegetconfiguredpipe.md) | The WdfUsbInterfaceGetConfiguredPipe method returns a handle to the framework pipe object that is associated with a specified USB device interface and pipe index. Optionally, the method also returns information about the pipe. |
| [WdfUsbInterfaceGetConfiguredSettingIndex function](nf-wdfusb-wdfusbinterfacegetconfiguredsettingindex.md) | The WdfUsbInterfaceGetConfiguredSettingIndex method returns the alternate setting index that is currently selected for a specified USB device interface. |
| [WdfUsbInterfaceGetDescriptor function](nf-wdfusb-wdfusbinterfacegetdescriptor.md) | The WdfUsbInterfaceGetDescriptor method retrieves the USB interface descriptor that is associated with a specified alternate setting of a specified USB interface. |
| [WdfUsbInterfaceGetEndpointInformation function](nf-wdfusb-wdfusbinterfacegetendpointinformation.md) | The WdfUsbInterfaceGetEndpointInformation method retrieves information about a specified USB device endpoint and its associated pipe. |
| [WdfUsbInterfaceGetInterfaceNumber function](nf-wdfusb-wdfusbinterfacegetinterfacenumber.md) | The WdfUsbInterfaceGetInterfaceNumber method returns the interface number of a specified USB interface object. |
| [WdfUsbInterfaceGetNumConfiguredPipes function](nf-wdfusb-wdfusbinterfacegetnumconfiguredpipes.md) | The WdfUsbInterfaceGetNumConfiguredPipes method returns the number of pipes that are configured for a specified USB device interface. |
| [WdfUsbInterfaceGetNumEndpoints function](nf-wdfusb-wdfusbinterfacegetnumendpoints.md) | The WdfUsbInterfaceGetNumEndpoints method returns the number of endpoints that are associated with a specified alternate setting of a specified USB interface. |
| [WdfUsbInterfaceGetNumSettings function](nf-wdfusb-wdfusbinterfacegetnumsettings.md) | The WdfUsbInterfaceGetNumSettings method returns the number of alternate settings that a specified USB interface supports. |
| [WdfUsbInterfaceSelectSetting function](nf-wdfusb-wdfusbinterfaceselectsetting.md) | The WdfUsbInterfaceSelectSetting method selects a specified alternate setting for a specified USB interface. |
| [WdfUsbTargetDeviceAllocAndQueryString function](nf-wdfusb-wdfusbtargetdeviceallocandquerystring.md) | The WdfUsbTargetDeviceAllocAndQueryString method allocates a buffer, then it retrieves the Unicode string that is associated with a specified USB device and descriptor index value. |
| [WdfUsbTargetDeviceCreate function](nf-wdfusb-wdfusbtargetdevicecreate.md) | The WdfUsbTargetDeviceCreate method creates a framework USB device object for a specified framework device object and opens the USB device for I/O operations. |
| [WdfUsbTargetDeviceCreateIsochUrb function](nf-wdfusb-wdfusbtargetdevicecreateisochurb.md) | The WdfUsbTargetDeviceCreateIsochUrb method allocates an isochronous USB request block (URB). |
| [WdfUsbTargetDeviceCreateUrb function](nf-wdfusb-wdfusbtargetdevicecreateurb.md) | The WdfUsbTargetDeviceCreateUrb method allocates a USB request block (URB). |
| [WdfUsbTargetDeviceCreateWithParameters function](nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md) | The WdfUsbTargetDeviceCreateWithParameters method creates a framework USB device object for a specified framework device object and opens the USB device for I/O operations. |
| [WdfUsbTargetDeviceCyclePortSynchronously function](nf-wdfusb-wdfusbtargetdevicecycleportsynchronously.md) | The WdfUsbTargetDeviceCyclePortSynchronously method power-cycles the USB port to which a specified device is attached. |
| [WdfUsbTargetDeviceFormatRequestForControlTransfer function](nf-wdfusb-wdfusbtargetdeviceformatrequestforcontroltransfer.md) | The WdfUsbTargetDeviceFormatRequestForControlTransfer method builds a USB control transfer request, but it does not send the request. |
| [WdfUsbTargetDeviceFormatRequestForCyclePort function](nf-wdfusb-wdfusbtargetdeviceformatrequestforcycleport.md) | The WdfUsbTargetDeviceFormatRequestForCyclePort method builds a power-cycle request for the port to which a specified device is attached, but it does not send the request. |
| [WdfUsbTargetDeviceFormatRequestForString function](nf-wdfusb-wdfusbtargetdeviceformatrequestforstring.md) | The WdfUsbTargetDeviceFormatRequestForString method builds a request for the USB string descriptor that is associated with a USB device's string index value. |
| [WdfUsbTargetDeviceFormatRequestForUrb function](nf-wdfusb-wdfusbtargetdeviceformatrequestforurb.md) | The WdfUsbTargetDeviceFormatRequestForUrb method builds an USB request for a specified USB device, using request parameters that are described by a URB, but it does not send the request. |
| [WdfUsbTargetDeviceGetDeviceDescriptor function](nf-wdfusb-wdfusbtargetdevicegetdevicedescriptor.md) | The WdfUsbTargetDeviceGetDeviceDescriptor method retrieves the USB device descriptor for the USB device that is associated with a specified framework USB device object. |
| [WdfUsbTargetDeviceGetInterface function](nf-wdfusb-wdfusbtargetdevicegetinterface.md) | The WdfUsbTargetDeviceGetInterface method returns a handle to the framework USB interface object that is associated with a specified interface index. |
| [WdfUsbTargetDeviceGetIoTarget function](nf-wdfusb-wdfusbtargetdevicegetiotarget.md) | The WdfUsbTargetDeviceGetIoTarget method returns a handle to the I/O target object that is associated with a specified USB device. |
| [WdfUsbTargetDeviceGetNumInterfaces function](nf-wdfusb-wdfusbtargetdevicegetnuminterfaces.md) | The WdfUsbTargetDeviceGetNumInterfaces method returns the number of USB device interfaces that are supported by a specified USB device. |
| [WdfUsbTargetDeviceIsConnectedSynchronous function](nf-wdfusb-wdfusbtargetdeviceisconnectedsynchronous.md) | The WdfUsbTargetDeviceIsConnectedSynchronous method determines if the specified USB device is connected. |
| [WdfUsbTargetDeviceQueryString function](nf-wdfusb-wdfusbtargetdevicequerystring.md) | The WdfUsbTargetDeviceQueryString method retrieves the Unicode string that is associated with a specified USB device and descriptor index value. |
| [WdfUsbTargetDeviceQueryUsbCapability function](nf-wdfusb-wdfusbtargetdevicequeryusbcapability.md) | The WdfUsbTargetDeviceQueryUsbCapability method determines whether the host controller and USB driver stack support a specific capability. |
| [WdfUsbTargetDeviceResetPortSynchronously function](nf-wdfusb-wdfusbtargetdeviceresetportsynchronously.md) | The WdfUsbTargetDeviceResetPortSynchronously method resets the USB port that is associated with the specified USB device. |
| [WdfUsbTargetDeviceRetrieveConfigDescriptor function](nf-wdfusb-wdfusbtargetdeviceretrieveconfigdescriptor.md) | The WdfUsbTargetDeviceRetrieveConfigDescriptor method retrieves the USB configuration descriptor for the USB device that is associated with a specified framework USB device object. |
| [WdfUsbTargetDeviceRetrieveCurrentFrameNumber function](nf-wdfusb-wdfusbtargetdeviceretrievecurrentframenumber.md) | The WdfUsbTargetDeviceRetrieveCurrentFrameNumber method retrieves the current USB frame number. |
| [WdfUsbTargetDeviceRetrieveInformation function](nf-wdfusb-wdfusbtargetdeviceretrieveinformation.md) | The WdfUsbTargetDeviceRetrieveInformation method retrieves information about the USB device that is associated with a specified framework USB device object. |
| [WdfUsbTargetDeviceSelectConfig function](nf-wdfusb-wdfusbtargetdeviceselectconfig.md) | The WdfUsbTargetDeviceSelectConfig method selects a USB configuration for a device, or it deconfigures the device. |
| [WdfUsbTargetDeviceSendControlTransferSynchronously function](nf-wdfusb-wdfusbtargetdevicesendcontroltransfersynchronously.md) | The WdfUsbTargetDeviceSendControlTransferSynchronously method builds a USB control transfer request and sends it synchronously to an I/O target. |
| [WdfUsbTargetDeviceSendUrbSynchronously function](nf-wdfusb-wdfusbtargetdevicesendurbsynchronously.md) | The WdfUsbTargetDeviceSendUrbSynchronously method sends a USB request synchronously to a specified USB device, using request parameters that are described by a URB. |
| [WdfUsbTargetDeviceWdmGetConfigurationHandle function](nf-wdfusb-wdfusbtargetdevicewdmgetconfigurationhandle.md) | The WdfUsbTargetDeviceWdmGetConfigurationHandle method returns the USBD_CONFIGURATION_HANDLE-typed handle that is associated with the current configuration of a specified USB device. |
| [WdfUsbTargetPipeAbortSynchronously function](nf-wdfusb-wdfusbtargetpipeabortsynchronously.md) | The WdfUsbTargetPipeAbortSynchronously method builds an abort request and sends it synchronously to a specified USB pipe. |
| [WdfUsbTargetPipeConfigContinuousReader function](nf-wdfusb-wdfusbtargetpipeconfigcontinuousreader.md) | The WdfUsbTargetPipeConfigContinuousReader method configures the framework to continuously read from a specified USB pipe. |
| [WdfUsbTargetPipeFormatRequestForAbort function](nf-wdfusb-wdfusbtargetpipeformatrequestforabort.md) | The WdfUsbTargetPipeFormatRequestForAbort method builds an abort request for a specified USB pipe, but it does not send the request. |
| [WdfUsbTargetPipeFormatRequestForRead function](nf-wdfusb-wdfusbtargetpipeformatrequestforread.md) | The WdfUsbTargetPipeFormatRequestForRead method builds a read request for a USB input pipe, but it does not send the request. |
| [WdfUsbTargetPipeFormatRequestForReset function](nf-wdfusb-wdfusbtargetpipeformatrequestforreset.md) | The WdfUsbTargetPipeFormatRequestForReset method builds a reset request for a specified USB pipe, but it does not send the request. |
| [WdfUsbTargetPipeFormatRequestForUrb function](nf-wdfusb-wdfusbtargetpipeformatrequestforurb.md) | The WdfUsbTargetPipeFormatRequestForUrb method builds an USB request for a specified USB pipe, using request parameters that a specified URB describes, but it does not send the request. |
| [WdfUsbTargetPipeFormatRequestForWrite function](nf-wdfusb-wdfusbtargetpipeformatrequestforwrite.md) | The WdfUsbTargetPipeFormatRequestForWrite method builds a write request for a USB output pipe, but it does not send the request. |
| [WdfUsbTargetPipeGetInformation function](nf-wdfusb-wdfusbtargetpipegetinformation.md) | The WdfUsbTargetPipeGetInformation method retrieves information about a USB pipe and its endpoint. |
| [WdfUsbTargetPipeGetIoTarget function](nf-wdfusb-wdfusbtargetpipegetiotarget.md) | The WdfUsbTargetPipeGetIoTarget method returns a handle to the I/O target object that is associated with a specified USB pipe. |
| [WdfUsbTargetPipeGetType function](nf-wdfusb-wdfusbtargetpipegettype.md) | The WdfUsbTargetPipeGetType method returns the type of a specified USB pipe. |
| [WdfUsbTargetPipeIsInEndpoint function](nf-wdfusb-wdfusbtargetpipeisinendpoint.md) | The WdfUsbTargetPipeIsInEndpoint method determines whether a specified USB pipe is connected to an input endpoint. |
| [WdfUsbTargetPipeIsOutEndpoint function](nf-wdfusb-wdfusbtargetpipeisoutendpoint.md) | The WdfUsbTargetPipeIsOutEndpoint method determines whether a specified USB pipe is connected to an output endpoint. |
| [WdfUsbTargetPipeReadSynchronously function](nf-wdfusb-wdfusbtargetpipereadsynchronously.md) | The WdfUsbTargetPipeReadSynchronously method builds a read request and sends it synchronously to a specified USB input pipe. |
| [WdfUsbTargetPipeResetSynchronously function](nf-wdfusb-wdfusbtargetpiperesetsynchronously.md) | The WdfUsbTargetPipeResetSynchronously method builds a reset request and sends it synchronously to a specified USB pipe. |
| [WdfUsbTargetPipeSendUrbSynchronously function](nf-wdfusb-wdfusbtargetpipesendurbsynchronously.md) | The WdfUsbTargetPipeSendUrbSynchronously method builds an USB request for a specified USB pipe, using request parameters that a specified URB describes. |
| [WdfUsbTargetPipeSetNoMaximumPacketSizeCheck function](nf-wdfusb-wdfusbtargetpipesetnomaximumpacketsizecheck.md) | The WdfUsbTargetPipeSetNoMaximumPacketSizeCheck method disables the framework's test of whether the size of a driver's read buffer is a multiple of a USB pipe's maximum packet size. |
| [WdfUsbTargetPipeWdmGetPipeHandle function](nf-wdfusb-wdfusbtargetpipewdmgetpipehandle.md) | The WdfUsbTargetPipeWdmGetPipeHandle method returns the USBD_PIPE_HANDLE-typed handle that is associated with a specified framework pipe object. |
| [WdfUsbTargetPipeWriteSynchronously function](nf-wdfusb-wdfusbtargetpipewritesynchronously.md) | The WdfUsbTargetPipeWriteSynchronously method builds a write request and sends it synchronously to a specified USB output pipe. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [EVT_WDF_USB_READERS_FAILED callback](nc-wdfusb-evt_wdf_usb_readers_failed.md) | A driver's EvtUsbTargetPipeReadersFailed event callback function informs the driver that a continuous reader has reported an error while processing a read request. |
| [EVT_WDF_USB_READER_COMPLETION_ROUTINE callback](nc-wdfusb-evt_wdf_usb_reader_completion_routine.md) | A driver's EvtUsbTargetPipeReadComplete event callback function informs the driver that a continuous reader has successfully completed a read request. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_WDF_USB_CONTINUOUS_READER_CONFIG structure](ns-wdfusb-_wdf_usb_continuous_reader_config.md) | The WDF_USB_CONTINUOUS_READER_CONFIG structure contains information that the framework uses to configure a continuous reader for a USB pipe. |
| [_WDF_USB_CONTROL_SETUP_PACKET structure](ns-wdfusb-_wdf_usb_control_setup_packet.md) | The WDF_USB_CONTROL_SETUP_PACKET structure describes a setup packet for a USB control transfer. |
| [_WDF_USB_DEVICE_CREATE_CONFIG structure](ns-wdfusb-_wdf_usb_device_create_config.md) | The WDF_USB_DEVICE_CREATE_CONFIG structure contains information that the framework uses to configure a framework USB device object. |
| [_WDF_USB_DEVICE_INFORMATION structure](ns-wdfusb-_wdf_usb_device_information.md) | The WDF_USB_DEVICE_INFORMATION structure contains version and capability information for a USB device. |
| [_WDF_USB_DEVICE_SELECT_CONFIG_PARAMS structure](ns-wdfusb-_wdf_usb_device_select_config_params.md) | The WDF_USB_DEVICE_SELECT_CONFIG_PARAMS structure specifies USB device configuration parameters. |
| [_WDF_USB_INTERFACE_SELECT_SETTING_PARAMS structure](ns-wdfusb-_wdf_usb_interface_select_setting_params.md) | The WDF_USB_INTERFACE_SELECT_SETTING_PARAMS structure contains selection information for a USB interface. |
| [_WDF_USB_INTERFACE_SETTING_PAIR structure](ns-wdfusb-_wdf_usb_interface_setting_pair.md) | The WDF_USB_INTERFACE_SETTING_PAIR structure specifies an alternate setting for a specified USB interface. |
| [_WDF_USB_PIPE_INFORMATION structure](ns-wdfusb-_wdf_usb_pipe_information.md) | The WDF_USB_PIPE_INFORMATION structure contains information about a USB pipe and its endpoint. |
| [_WDF_USB_REQUEST_COMPLETION_PARAMS structure](ns-wdfusb-_wdf_usb_request_completion_params.md) | The WDF_USB_REQUEST_COMPLETION_PARAMS structure contains parameters that are associated with the completion of an I/O request for a USB device. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_WDF_USB_BMREQUEST_DIRECTION enumeration](ne-wdfusb-_wdf_usb_bmrequest_direction.md) | The WDF_USB_BMREQUEST_DIRECTION enumeration identifies the data transfer direction for a USB control transfer. |
| [_WDF_USB_BMREQUEST_RECIPIENT enumeration](ne-wdfusb-_wdf_usb_bmrequest_recipient.md) | The WDF_USB_BMREQUEST_RECIPIENT enumeration identifies the data transfer recipient for a USB control transfer. |
| [_WDF_USB_BMREQUEST_TYPE enumeration](ne-wdfusb-_wdf_usb_bmrequest_type.md) | The WDF_USB_BMREQUEST_TYPE enumeration identifies the data transfer type for a USB control transfer. |
| [_WDF_USB_DEVICE_TRAITS enumeration](ne-wdfusb-_wdf_usb_device_traits.md) | The WDF_USB_DEVICE_TRAITS enumeration identifies USB device traits. |
| [_WDF_USB_PIPE_TYPE enumeration](ne-wdfusb-_wdf_usb_pipe_type.md) | The WDF_USB_PIPE_TYPE enumeration identifies the types of USB pipes. |
| [_WDF_USB_REQUEST_TYPE enumeration](ne-wdfusb-_wdf_usb_request_type.md) | The WDF_USB_REQUEST_TYPE enumeration identifies the types of USB requests that a framework-based driver can send to a USB I/O target. |
| [_WdfUsbTargetDeviceSelectConfigType enumeration](ne-wdfusb-_wdfusbtargetdeviceselectconfigtype.md) | The WdfUsbTargetDeviceSelectConfigType enumeration defines types of configuration operations for USB devices. |
| [_WdfUsbTargetDeviceSelectSettingType enumeration](ne-wdfusb-_wdfusbtargetdeviceselectsettingtype.md) | The WdfUsbTargetDeviceSelectSettingType enumeration defines techniques for specifying an alternate setting for a USB interface. |
