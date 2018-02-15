---
UID: NS:winbio_ioctl._WINBIO_SENSOR_ATTRIBUTES
title: "_WINBIO_SENSOR_ATTRIBUTES"
author: windows-driver-content
description: The IOCTL_BIOMETRIC_GET_ATTRIBUTES structure returns the WINBIO_SENSOR_ATTRIBUTES structure as output.
old-location: biometric\winbio_sensor_attributes.htm
old-project: biometric
ms.assetid: edfd5b49-f658-46c7-a3f3-221afb35abb7
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: winbio_ioctl/PWINBIO_SENSOR_ATTRIBUTES, _WINBIO_SENSOR_ATTRIBUTES, winbio_ioctl/WINBIO_SENSOR_ATTRIBUTES, WINBIO_SENSOR_ATTRIBUTES structure [Biometric Devices], biometric.winbio_sensor_attributes, biometric_ref_958b511b-a855-4897-87d8-f0d7bb4970ce.xml, *PWINBIO_SENSOR_ATTRIBUTES, PWINBIO_SENSOR_ATTRIBUTES structure pointer [Biometric Devices], WINBIO_SENSOR_ATTRIBUTES, PWINBIO_SENSOR_ATTRIBUTES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: winbio_ioctl.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	winbio_ioctl.h
apiname:
-	WINBIO_SENSOR_ATTRIBUTES
product: Windows
targetos: Windows
req.typenames: "*PWINBIO_SENSOR_ATTRIBUTES, WINBIO_SENSOR_ATTRIBUTES"
req.product: Windows 10 or later.
---

# _WINBIO_SENSOR_ATTRIBUTES structure


## -description


The <a href="..\winbio_ioctl\ni-winbio_ioctl-ioctl_biometric_get_attributes.md">IOCTL_BIOMETRIC_GET_ATTRIBUTES</a> structure returns the WINBIO_SENSOR_ATTRIBUTES structure as output.


## -syntax


````
typedef struct _WINBIO_SENSOR_ATTRIBUTES {
  DWORD                           PayloadSize;
  HRESULT                         WinBioHresult;
  WINBIO_VERSION                  WinBioVersion;
  WINBIO_BIOMETRIC_TYPE           SensorType;
  WINBIO_BIOMETRIC_SENSOR_SUBTYPE SensorSubType;
  WINBIO_CAPABILITIES             Capabilities;
  WINBIO_STRING                   ManufacturerName;
  WINBIO_STRING                   ModelName;
  WINBIO_STRING                   SerialNumber;
  WINBIO_VERSION                  FirmwareVersion;
  DWORD                           SupportedFormatEntries;
  WINBIO_REGISTERED_FORMAT        SupportedFormat[1];
} WINBIO_SENSOR_ATTRIBUTES, *PWINBIO_SENSOR_ATTRIBUTES;
````


## -struct-fields




### -field PayloadSize

A DWORD value that indicates the total size of the payload, including the fixed length structure and any variable data at the end.


### -field WinBioHresult

An HRESULT value that indicates containing status detail of the I/O operation.   The following table includes possible values.

<table>
<tr>
<th>Status value</th>
<th>Description</th>
</tr>
<tr>
<td>
S_OK

</td>
<td>
The operation completed successfully.

</td>
</tr>
<tr>
<td>
HRESULT_FROM_NT(STATUS_IO_DEVICE_ERROR)

</td>
<td>
The driver could not gather the necessary information from the device.

</td>
</tr>
</table>
 


### -field WinBioVersion

A structure of type <a href="..\winbio_types\ns-winbio_types-_winbio_version.md">WINBIO_VERSION</a> that contains a WinBio WBDI version that is supported by the driver. To be compatible with the WinBio service, <b>WinBioVersion</b> must contain the same major version as the current major version of the WinBio service, in addition to a minor version that is less than or equal to the current minor version of the WinBio service. 


### -field SensorType

A DWORD bitmask of type WINBIO_BIOMETRIC_TYPE that contains biometric data that is collected by the sensor. In Windows 7, only WINBIO_TYPE_FINGERPRINT is supported.


### -field SensorSubType

A WINBIO_BIOMETRIC_SENSOR_SUBTYPE subtype that contains additional information about the sensor.  For example, this member could specify whether the sensor requires the user to simply touch the sensor or swipe a finger over the sensor.

WINBIO_BIOMETRIC_SENSOR_SUBTYPE can contain the values in the following table.

<table>
<tr>
<th>
              
                Biometric subtype value
              
            </th>
<th>
              
                Description
              
            </th>
</tr>
<tr>
<td>
WINBIO_FP_SENSOR_SUBTYPE_SWIPE

</td>
<td>
The device requires the user to swipe their fingertip over the sensor.

</td>
</tr>
<tr>
<td>
WINBIO_FP_SENSOR_SUBTYPE_TOUCH

</td>
<td>
The device requires the user to place their entire fingerprint on a sensor pad.

</td>
</tr>
</table>
 


### -field Capabilities

A WINBIO_CAPABILITIES subtype, which indicates which capabilities are supported by the device. 

WINBIO_CAPABILITIES can contain the values in the following table.

<table>
<tr>
<th>
       
        Biometric capability value
       
      </th>
<th>
       
        Description
       
      </th>
</tr>
<tr>
<td>
WINBIO_CAPABILITY_SENSOR 

</td>
<td>
The device can collect biometric data.

</td>
</tr>
<tr>
<td>
WINBIO_CAPABILITY_MATCHING

</td>
<td>
The device can perform match operations.

</td>
</tr>
<tr>
<td>
WINBIO_CAPABILITY_STORAGE

</td>
<td>
The device can store biometric templates.

</td>
</tr>
<tr>
<td>
WINBIO_CAPABILITY_SECURE_STORAGE

</td>
<td>
The device can store secure data that is associated with a template.  The secure data is only released with a positive match.  The device must support at least the SHA-1 algorithm for secure hash computation to be used to store templates in the system pool.

</td>
</tr>
<tr>
<td>
WINBIO_CAPABILITY_PROCESSING

</td>
<td>
The device can process samples and turn them into biometric templates.

</td>
</tr>
<tr>
<td>
WINBIO_CAPABILITY_ENCRYPTION

</td>
<td>
The device supports encryption of samples and templates.

</td>
</tr>
<tr>
<td>
WINBIO_CAPABILITY_SIGNING

</td>
<td>
The device can sign captured data.

</td>
</tr>
<tr>
<td>
WINBIO_CAPABILITY_NAVIGATION

</td>
<td>
The device can be used as a navigation device.  Some devices and drivers can capture data in a format that can be translated by a user-mode application into navigation events, much like a mouse.

</td>
</tr>
<tr>
<td>
WINBIO_CAPABILITY_INDICATOR

</td>
<td>
The device has an indicator that can be turned on or off.

</td>
</tr>
<tr>
<td>
WINBIO_CAPABILITY_VIRTUAL_SENSOR

</td>
<td>
The sensor adapter manages its own connection to the biometric hardware.

<div class="alert"><b>Note</b>  This constant applies only for Windows 10 and later.</div>
<div> </div>
</td>
</tr>
<tr>
<td>
WINBIO_CAPABILITY_SECURE_SENSOR

</td>
<td>
The device supports security methods available in the WinBio engine adapter interface version 4.0  or later.

<div class="alert"><b>Note</b>  This constant applies only for Windows 10 and later.</div>
<div> </div>
</td>
</tr>
</table>
 


### -field ManufacturerName

 A structure of type WINBIO_STRING that contains the name of the device manufacturer.


### -field ModelName

 A structure of type WINBIO_STRING that contains the name of the device model.


### -field SerialNumber

A structure of type WINBIO_STRING that contains the serial number of the device, if one exists.


### -field FirmwareVersion

 A structure of type <a href="..\winbio_types\ns-winbio_types-_winbio_version.md">WINBIO_VERSION</a> that contains the version of the firmware that is loaded on the device.


### -field SupportedFormatEntries

 The number of formats that are supported by the driver and device.  There must be at least one, which is the Windows standard format.


### -field SupportedFormat

A structure of type <a href="..\winbio_types\ns-winbio_types-_winbio_registered_format.md">WINBIO_REGISTERED_FORMAT</a> that contains a list of the formats supported by the driver and device. 


## -see-also

<a href="..\winbio_ioctl\ni-winbio_ioctl-ioctl_biometric_get_attributes.md">IOCTL_BIOMETRIC_GET_ATTRIBUTES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [biometric\biometric]:%20WINBIO_SENSOR_ATTRIBUTES structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

