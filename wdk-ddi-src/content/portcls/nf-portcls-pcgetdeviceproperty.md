---
UID: NF:portcls.PcGetDeviceProperty
title: PcGetDeviceProperty function
author: windows-driver-content
description: The PcGetDeviceProperty function returns the requested device property from the registry.
old-location: audio\pcgetdeviceproperty.htm
old-project: audio
ms.assetid: 75d66965-ab97-4f67-b62f-e7fedbf524a6
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: audio.pcgetdeviceproperty, PcGetDeviceProperty, portcls/PcGetDeviceProperty, PcGetDeviceProperty function [Audio Devices], audpc-routines_c95326e5-dc8f-4a04-b31d-6c4e79cc6771.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: The PortCls system driver implements the PcGetDeviceProperty function in Microsoft Windows 98/Me and in Windows 2000 and later operating systems.
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
req.lib: Portcls.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	LibDef
apilocation: 
-	Portcls.lib
-	Portcls.dll
apiname: 
-	PcGetDeviceProperty
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# PcGetDeviceProperty function


## -description


The <b>PcGetDeviceProperty</b> function returns the requested device property from the registry.


## -syntax


````
NTSTATUS PcGetDeviceProperty(
  _In_  PVOID                    DeviceObject,
  _In_  DEVICE_REGISTRY_PROPERTY DeviceProperty,
  _In_  ULONG                    BufferLength,
  _Out_ PVOID                    PropertyBuffer,
  _Out_ PULONG                   ResultLength
);
````


## -parameters




### -param DeviceObject [in]

Pointer to the device object for the device. This parameter points to a <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> system structure but is cast to type PVOID.


### -param DeviceProperty [in]

Specifies the Plug and Play device property that is requested. For a list of property specifier values, see the following Remarks section.


### -param BufferLength [in]

Specifies the length in bytes of the buffer that is to receive the requested property data.


### -param PropertyBuffer [out]

Pointer to a caller-allocated buffer into which the method is to write the requested property data. The buffer must be large enough to contain the number of bytes specified in <i>BufferLength</i>.


### -param ResultLength [out]

Pointer to a caller-allocated variable into which the method outputs a count specifying the number of bytes actually written to the buffer. If the buffer size specified in <i>BufferLength</i> is too small to hold the property data, the method instead outputs the number of bytes required for the property data and returns STATUS_BUFFER_TOO_SMALL.


## -returns


<b>PcGetDeviceProperty</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code. The routine returns STATUS_BUFFER_TOO_SMALL if the buffer size specified in <i>BufferLength</i> was not large enough to contain the requested property data.



## -remarks


Set the <b>DeviceProperty</b> parameter to one of the following DEVICE_REGISTRY_PROPERTY enumeration values from header file wdm.h:

<b>DevicePropertyAddress</b>

<b>DevicePropertyBootConfiguration</b>

<b>DevicePropertyBootConfigurationTranslated</b>

<b>DevicePropertyBusNumber</b>

<b>DevicePropertyBusTypeGuid</b>

<b>DevicePropertyClassGuid</b>

<b>DevicePropertyClassName</b>

<b>DevicePropertyCompatibleIDs</b>

<b>DevicePropertyDetachability</b>

<b>DevicePropertyDeviceDescription</b>

<b>DevicePropertyDriverKeyName</b>

<b>DevicePropertyEnumeratorName</b>

<b>DevicePropertyFriendlyName</b>

<b>DevicePropertyHardwareID</b>

<b>DevicePropertyInstallState</b>

<b>DevicePropertyLegacyBusType</b>

<b>DevicePropertyLocationInformation</b>

<b>DevicePropertyManufacturer</b>

<b>DevicePropertyPhysicalDeviceObjectName</b>

<b>DevicePropertyUINumber</b>

For a description of the preceding DeviceProperty<i>Xxx</i> values, see <a href="..\wdm\nf-wdm-iogetdeviceproperty.md">IoGetDeviceProperty</a>.

Two calls to <b>PcGetDeviceProperty</b> might be necessary to determine the required <i>BufferLength</i>. In the first call, <i>BufferLength</i> can either be zero or a best-guess estimate of the required buffer size. If the return status is STATUS_BUFFER_TOO_SMALL, this means that the caller should allocate a buffer of the size that was output through <i>ResultLength</i> and call <b>PcGetDeviceProperty</b> again. 



## -see-also

<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>

<a href="..\wdm\nf-wdm-iogetdeviceproperty.md">IoGetDeviceProperty</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PcGetDeviceProperty function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

