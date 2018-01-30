---
UID: NF:usbdlib.USBD_ParseConfigurationDescriptorEx
title: USBD_ParseConfigurationDescriptorEx function
author: windows-driver-content
description: The USBD_ParseConfigurationDescriptorEx routine searches a given configuration descriptor and returns a pointer to an interface that matches the given search criteria.
old-location: buses\usbd_parseconfigurationdescriptorex.htm
old-project: usbref
ms.assetid: c14b3cde-b501-4d07-96ae-f0e0e6320966
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: USBD_ParseConfigurationDescriptorEx routine [Buses], buses.usbd_parseconfigurationdescriptorex, USBD_ParseConfigurationDescriptorEx, usbdlib/USBD_ParseConfigurationDescriptorEx, usbfunc_c493d121-9821-4381-b756-fa417c8f5f93.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: usbdlib.h
req.include-header: Usbdlib.h
req.target-type: Universal
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
req.lib: Usbd.lib
req.dll: 
req.irql: "< DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Usbd.lib
-	Usbd.dll
apiname:
-	USBD_ParseConfigurationDescriptorEx
product: Windows
targetos: Windows
req.typenames: "*PUSBCAMD_DEVICE_DATA2, USBCAMD_DEVICE_DATA2"
req.product: Windows 10 or later.
---

# USBD_ParseConfigurationDescriptorEx function


## -description


The <b>USBD_ParseConfigurationDescriptorEx</b> routine searches a given configuration descriptor and returns a pointer to an interface that matches the given search criteria.


## -syntax


````
PUSB_INTERFACE_DESCRIPTOR USBD_ParseConfigurationDescriptorEx(
  _In_ PUSB_CONFIGURATION_DESCRIPTOR ConfigurationDescriptor,
  _In_ PVOID                         StartPosition,
  _In_ LONG                          InterfaceNumber,
  _In_ LONG                          AlternateSetting,
  _In_ LONG                          InterfaceClass,
  _In_ LONG                          InterfaceSubClass,
  _In_ LONG                          InterfaceProtocol
);
````


## -parameters




### -param ConfigurationDescriptor [in]

Pointer to a USB configuration descriptor that contains the interface for which to search.


### -param StartPosition [in]

Pointer to the address within the configuration descriptor, provided at <i>ConfigurationDescriptor</i>, to begin searching from. To search from the beginning of the configuration descriptor, the parameters <i>ConfigurationDescriptor</i> and <i>StartPosition</i> must be the same address.


### -param InterfaceNumber [in]

Specifies the device-defined index of the interface to be retrieved. This should be set to -1 if it should not be a search criterion.


### -param AlternateSetting [in]

Specifies the device-defined alternate-setting index of the interface to be retrieved. If the caller does not wish the alternate setting value to be a search criterion, this parameter should be set to -1.


### -param InterfaceClass [in]

Specifies the device- or USB-defined identifier for the interface class of the interface to be retrieved. If the caller does not wish the interface class value to be a search criterion, this parameter should be set to -1.


### -param InterfaceSubClass [in]

Specifies the device- or USB-defined identifier for the interface subclass of the interface to be retrieved. If the caller does not wish the interface subclass value to be a search criterion, this parameter should be set to -1.


### -param InterfaceProtocol [in]

Specifies the device- or USB-defined identifier for the interface protocol of the interface to be retrieved. If the caller does not wish the interface protocol value to be a search criterion, this parameter should be set to -1.


## -returns


<b>USBD_ParseConfigurationDescriptorEx</b> returns a pointer to the first interface descriptor that matches the given search criteria. If no interface matches the search criteria, it returns <b>NULL</b>.



## -remarks


Callers can specify more than one of the search criteria (InterfaceNumber, AlternateSetting, InterfaceClass, InterfaceSubClass, and InterfaceProtocol) when using this routine to find an interface within a configuration descriptor. For example code, see <a href="..\usbdlib\nf-usbdlib-usbd_createconfigurationrequestex.md">USBD_CreateConfigurationRequestEx</a>.

When this routine parses the configuration descriptor looking for the interface descriptor that matches the search criteria, it returns the first match, terminating the search. Callers should specify as many search criteria as are necessary to find the desired interface.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540134">USB device driver programming reference</a>

<a href="..\usbspec\ns-usbspec-_usb_configuration_descriptor.md">USB_CONFIGURATION_DESCRIPTOR</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBD_ParseConfigurationDescriptorEx routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

