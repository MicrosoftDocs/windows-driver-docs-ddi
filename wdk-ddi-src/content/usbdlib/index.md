---
UID: NA:usbdlib
ms.assetid: e417fbda-5320-3e5a-a7d9-7f8a4a5448cd
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Usbdlib.h header



This header is used by Universal Serial Bus(USB). For more information, see
- [Universal Serial Bus(USB)](../_usbref/index.md)

Usbdlib.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [COMPOSITE_DEVICE_CAPABILITIES_INIT function](nf-usbdlib-composite_device_capabilities_init.md) | The COMPOSITE_DEVICE_CAPABILITIES_INIT macro initializes the COMPOSITE_DEVICE_CAPABILITIES structure. |
| [USBD_AssignUrbToIoStackLocation function](nf-usbdlib-usbd_assignurbtoiostacklocation.md) | The USBD_AssignUrbToIoStackLocation routine is called by a client driver to associate an URB with the IRP's next stack location. |
| [USBD_BuildRegisterCompositeDevice function](nf-usbdlib-usbd_buildregistercompositedevice.md) | The USBD_BuildRegisterCompositeDevice routine is called by the driver of a USB multi-function device (composite driver) to initialize a REGISTER_COMPOSITE_DEVICE structure with the information required for registering the driver with the USB driver stack. |
| [USBD_CalculateUsbBandwidth function](nf-usbdlib-usbd_calculateusbbandwidth.md) | The USBD_CalculateUsbBandwidth routine has been deprecated in Windows XP and later operating systems. Do not use. |
| [USBD_CloseHandle function](nf-usbdlib-usbd_closehandle.md) | The USBD_CloseHandle routine is called by a USB client driver to close a USBD handle and release all resources associated with the driver's registration. |
| [USBD_CreateConfigurationRequest function](nf-usbdlib-usbd_createconfigurationrequest.md) | The USBD_CreateConfigurationRequest routine has been deprecated. Use USBD_CreateConfigurationRequestEx instead. |
| [USBD_CreateConfigurationRequestEx function](nf-usbdlib-usbd_createconfigurationrequestex.md) | The USBD_CreateConfigurationRequestEx routine allocates and formats a URB to select a configuration for a USB device.USBD_CreateConfigurationRequestEx replaces USBD_CreateConfigurationRequest. |
| [USBD_CreateHandle function](nf-usbdlib-usbd_createhandle.md) | The USBD_CreateHandle routine is called by a WDM USB client driver to obtain a USBD handle. The routine registers the client driver with the underlying USB driver stack. |
| [USBD_GetInterfaceLength function](nf-usbdlib-usbd_getinterfacelength.md) | The USBD_GetInterfaceLength routine obtains the length of a given interface descriptor, including the length of all endpoint descriptors contained within the interface. |
| [USBD_GetPdoRegistryParameter function](nf-usbdlib-usbd_getpdoregistryparameter.md) | The USBD_GetPdoRegistryParameter routine retrieves the value from the specified key in the USB device's hardware registry. |
| [USBD_GetUSBDIVersion function](nf-usbdlib-usbd_getusbdiversion.md) | The USBD_GetUSBDIVersion routine returns version information about the host controller driver (HCD) that controls the client's USB device.Note  USBD_IsInterfaceVersionSupported replaces the USBD_GetUSBDIVersion routine |
| [USBD_IsInterfaceVersionSupported function](nf-usbdlib-usbd_isinterfaceversionsupported.md) | The USBD_IsInterfaceVersionSupported routine is called by a USB client driver to check whether the underlying USB driver stack supports a particular USBD interface version. |
| [USBD_IsochUrbAllocate function](nf-usbdlib-usbd_isochurballocate.md) | The USBD_IsochUrbAllocate routine allocates and formats a URB structure for an isochronous transfer request. |
| [USBD_ParseConfigurationDescriptor function](nf-usbdlib-usbd_parseconfigurationdescriptor.md) | The USBD_ParseConfigurationDescriptor routine has been deprecated. Use USBD_ParseConfigurationDescriptorEx instead. |
| [USBD_ParseConfigurationDescriptorEx function](nf-usbdlib-usbd_parseconfigurationdescriptorex.md) | The USBD_ParseConfigurationDescriptorEx routine searches a given configuration descriptor and returns a pointer to an interface that matches the given search criteria. |
| [USBD_ParseDescriptors function](nf-usbdlib-usbd_parsedescriptors.md) | The USBD_ParseDescriptors routine searches a given configuration descriptor and returns a pointer to the first descriptor that matches the search criteria. |
| [USBD_QueryBusTime function](nf-usbdlib-usbd_querybustime.md) | The USBD_QueryBusTime routine has been deprecated in Windows XP and later operating systems. Do not use. |
| [USBD_QueryUsbCapability function](nf-usbdlib-usbd_queryusbcapability.md) | The USBD_QueryUsbCapability routine is called by a WDM client driver to determine whether the underlying USB driver stack and the host controller hardware support a specific capability. |
| [USBD_RegisterHcFilter function](nf-usbdlib-usbd_registerhcfilter.md) | The USBD_RegisterHcFilter routine has been deprecated in Windows XP and later operating systems. |
| [USBD_SelectConfigUrbAllocateAndBuild function](nf-usbdlib-usbd_selectconfigurballocateandbuild.md) | The USBD_SelectConfigUrbAllocateAndBuild routine allocates and formats a URB structure that is required to select a configuration for a USB device. |
| [USBD_SelectInterfaceUrbAllocateAndBuild function](nf-usbdlib-usbd_selectinterfaceurballocateandbuild.md) | The USBD_SelectInterfaceUrbAllocateAndBuild routine allocates and formats a URB structure that is required for a request to select an interface or change its alternate setting. |
| [USBD_UrbAllocate function](nf-usbdlib-usbd_urballocate.md) | The USBD_UrbAllocate routine allocates a USB Request Block (URB). |
| [USBD_UrbFree function](nf-usbdlib-usbd_urbfree.md) | The USBD_UrbFree routine releases the URB that is allocated by USBD_UrbAllocate, USBD_IsochUrbAllocate, USBD_SelectConfigUrbAllocateAndBuild, or USBD_SelectInterfaceUrbAllocateAndBuild. |
| [USBD_ValidateConfigurationDescriptor function](nf-usbdlib-usbd_validateconfigurationdescriptor.md) | The USBD_ValidateConfigurationDescriptor routine validates all descriptors returned by a device in its response to a configuration descriptor request. |
| [UsbBuildOpenStaticStreamsRequest function](nf-usbdlib-usbbuildopenstaticstreamsrequest.md) | The UsbBuildOpenStaticStreamsRequest inline function formats an URB structure for an open-streams request. The request opens streams associated with the specified bulk endpoint. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_COMPOSITE_DEVICE_CAPABILITIES structure](ns-usbdlib-_composite_device_capabilities.md) | The COMPOSITE_DEVICE_CAPABILITIES structure specifies the capabilities of the driver of a USB multi-function device (composite driver). To initialize the structure, use the COMPOSITE_DEVICE_CAPABILITIES_INIT macro. |
| [_REGISTER_COMPOSITE_DEVICE structure](ns-usbdlib-_register_composite_device.md) | The REGISTER_COMPOSITE_DEVICE structure is used with the IOCTL_INTERNAL_USB_REGISTER_COMPOSITE_DEVICE I/O control request to register a parent driver of a Universal Serial Bus (USB) multi-function device (composite driver) with the USB driver stack. |
| [_REQUEST_REMOTE_WAKE_NOTIFICATION structure](ns-usbdlib-_request_remote_wake_notification.md) | The purpose of the REQUEST_REMOTE_WAKE_NOTIFICATION structure is to specify input parameters for the IOCTL_INTERNAL_USB_REQUEST_REMOTE_WAKE_NOTIFICATION I/O control request. |
| [_USBD_INTERFACE_LIST_ENTRY structure](ns-usbdlib-_usbd_interface_list_entry.md) | The USBD_INTERFACE_LIST_ENTRY structure is used by USB client drivers to create an array of interfaces to be inserted into a configuration request. |

## Macros

| Title   | Description   |
| ---- |:---- |
| [GET_ISO_URB_SIZE macro](nf-usbdlib-get_iso_urb_size.md) | The GET_ISO_URB_SIZE macro returns the number of bytes required to hold an isochronous transfer request. |
| [UsbBuildGetStatusRequest macro](nf-usbdlib-usbbuildgetstatusrequest.md) | The UsbBuildGetStatusRequest macro formats an URB to obtain status from a device, interface, endpoint, or other device-defined target on a USB device. |
| [UsbBuildInterruptOrBulkTransferRequest macro](nf-usbdlib-usbbuildinterruptorbulktransferrequest.md) | The UsbBuildInterruptOrBulkTransferRequest macro formats an URB to send or receive data on a bulk pipe, or to receive data from an interrupt pipe. |
