---
UID: NS:udecxusbdevice._UDECX_ENDPOINTS_CONFIGURE_PARAMS
title: "_UDECX_ENDPOINTS_CONFIGURE_PARAMS"
author: windows-driver-content
description: Contains the configuration options specified by USB device emulation class extension (UdeCx) to the client driver when the class extension invokes EVT_UDECX_USB_DEVICE_ENDPOINTS_CONFIGURE.
old-location: buses\udecx_endpoints_configure_params.htm
old-project: usbref
ms.assetid: C31AE3A8-CD3C-4270-BA5C-A61C0F386701
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: "_UDECX_ENDPOINTS_CONFIGURE_PARAMS, buses.udecx_endpoints_configure_params, udecxusbdevice/UDECX_ENDPOINTS_CONFIGURE_PARAMS, udecxusbdevice/PUDECX_ENDPOINTS_CONFIGURE_PARAMS, *PUDECX_ENDPOINTS_CONFIGURE_PARAMS, PUDECX_ENDPOINTS_CONFIGURE_PARAMS structure pointer [Buses], UDECX_ENDPOINTS_CONFIGURE_PARAMS, UDECX_ENDPOINTS_CONFIGURE_PARAMS structure [Buses], PUDECX_ENDPOINTS_CONFIGURE_PARAMS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: udecxusbdevice.h
req.include-header: Udecx.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	UdecxUsbDevice.h
apiname:
-	UDECX_ENDPOINTS_CONFIGURE_PARAMS
product: Windows
targetos: Windows
req.typenames: "*PUDECX_ENDPOINTS_CONFIGURE_PARAMS, UDECX_ENDPOINTS_CONFIGURE_PARAMS"
req.product: Windows 10 or later.
---

# _UDECX_ENDPOINTS_CONFIGURE_PARAMS structure


## -description


Contains the configuration options specified by USB device emulation class extension (UdeCx) to the client driver when the class extension invokes <a href="..\udecxusbdevice\nc-udecxusbdevice-evt_udecx_usb_device_endpoints_configure.md">EVT_UDECX_USB_DEVICE_ENDPOINTS_CONFIGURE</a>.


## -syntax


````
typedef struct _UDECX_ENDPOINTS_CONFIGURE_PARAMS {
  ULONG                                                    Size;
  UDECX_ENDPOINTS_CONFIGURE_TYPE                           ConfigureType;
  UCHAR                                                    NewConfigurationValue;
  UCHAR                                                    InterfaceNumber;
  ULONG                                                    NewInterfaceSetting;
  UCHAR                                                    EndpointsToConfigureCount;
  _Field_size_(EndpointsToConfigureCount) UDECXUSBENDPOINT *EndpointsToConfigure;
  UCHAR                                                    ReleasedEndpointsCount;
  _Field_size_(ReleasedEndpointsCount) UDECXUSBENDPOINT    *EndpointsToConfigure;
} UDECX_ENDPOINTS_CONFIGURE_PARAMS, *PUDECX_ENDPOINTS_CONFIGURE_PARAMS;
````


## -struct-fields




### -field Size

Size of this structure.


### -field ConfigureType

A <a href="..\udecxusbdevice\ne-udecxusbdevice-_udecx_endpoints_configure_type.md">UDECX_ENDPOINTS_CONFIGURE_TYPE</a>-typed value that indicates whether the configuration, interface setting, or endpoint must be configured. 


### -field NewConfigurationValue

If <b>ConfigureType</b> is <b>UdecxEndpointsConfigureTypeDeviceConfigurationChange</b>, this value is <b>bConfigurationValue</b> of the new configuration descriptor (<a href="..\usbspec\ns-usbspec-_usb_configuration_descriptor.md">USB_CONFIGURATION_DESCRIPTOR</a>).


### -field InterfaceNumber

If <b>ConfigureType</b> is <b>UdecxEndpointsConfigureTypeInterfaceSettingChange</b>, this value is <b>bInterfaceNumber</b> of the current interface descriptor (<a href="..\usbspec\ns-usbspec-_usb_interface_descriptor.md">USB_INTERFACE_DESCRIPTOR</a>).


### -field NewInterfaceSetting

If <b>ConfigureType</b> is <b>UdecxEndpointsConfigureTypeInterfaceSettingChange</b>, this value is <b>bAlternateSetting</b> of the interface descriptor (<a href="..\usbspec\ns-usbspec-_usb_interface_descriptor.md">USB_INTERFACE_DESCRIPTOR</a>) to set.


### -field EndpointsToConfigureCount

The number entries in the array pointed to by <i>EndpointsToConfigure</i>. This value indicates number of endpoints that must be configured.


### -field EndpointsToConfigure

A pointer to an array of UDECXUSBENDPOINT handles that indicates the endpoint objects to be configured.

A pointer to an array of UDECXUSBENDPOINT handles that indicates the endpoint objects that must be released.


### -field ReleasedEndpointsCount

The number entries in the array pointed to by <i>EndpointsToConfigure</i>. This value indicates number of endpoints to release.


### -field ReleasedEndpoints

 




## -see-also

<a href="..\udecxusbdevice\nc-udecxusbdevice-evt_udecx_usb_device_endpoints_configure.md">EVT_UDECX_USB_DEVICE_ENDPOINTS_CONFIGURE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UDECX_ENDPOINTS_CONFIGURE_PARAMS structure%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

