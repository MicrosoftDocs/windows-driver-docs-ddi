---
UID: NF:wdm.IoGetDeviceProperty
title: IoGetDeviceProperty function
author: windows-driver-content
description: The IoGetDeviceProperty routine retrieves information about a device such as configuration information and the name of its PDO.
old-location: kernel\iogetdeviceproperty.htm
old-project: kernel
ms.assetid: 8c3b7f81-ea6e-47ae-a396-58826d097f1f
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: IoGetDeviceProperty, IoGetDeviceProperty routine [Kernel-Mode Driver Architecture], k104_b6185e0d-5e39-4671-ab50-07fe5eda3606.xml, kernel.iogetdeviceproperty, wdm/IoGetDeviceProperty
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoGetDeviceProperty
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoGetDeviceProperty function


## -description


The <b>IoGetDeviceProperty</b> routine retrieves information about a device such as configuration information and the name of its PDO.


## -parameters




### -param DeviceObject [in]

Pointer to the physical device object (PDO) for the device being queried.


### -param DeviceProperty [in]

Specifies the device property being requested. Must be one of the following <a href="https://msdn.microsoft.com/a17b4a88-45e8-45e7-b879-2f41b97be368">DEVICE_REGISTRY_PROPERTY</a> enumeration values:





#### DevicePropertyAddress

Requests the address of the device on the bus. <i>PropertyBuffer</i> points to a ULONG.

The interpretation of this address is bus-specific. The caller of this routine should call the routine again to request the <b>DevicePropertyBusTypeGuid</b>, or possibly the <b>DevicePropertyLegacyBusType</b>, so it can interpret the address. An address value of 0xFFFFFFFF indicates that the underlying bus driver did not supply a bus address for the device.



#### DevicePropertyBootConfiguration

Requests the hardware resources assigned to the device by the firmware, in raw form. <i>PropertyBuffer</i> points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541994">CM_RESOURCE_LIST</a> structure.



#### DevicePropertyBootConfigurationTranslated

The hardware resources assigned to the device by the firmware, in translated form. <i>PropertyBuffer</i> points to a <b>CM_RESOURCE_LIST</b> structure.



#### DevicePropertyBusNumber

Requests the legacy bus number of the bus the device is connected to. <i>PropertyBuffer</i> points to a ULONG.



#### DevicePropertyBusTypeGuid

Requests the GUID for the bus that the device is connected to. The system-defined bus type GUIDs are listed in the Wdmguid.h header file. <i>PropertyBuffer</i> points to a GUID, which is a 16-byte structure that contains the GUID in binary form.



#### DevicePropertyClassGuid

Requests the GUID for the device's setup class. <i>PropertyBuffer</i> points to a NULL-terminated array of WCHAR. This routine returns the GUID in a string format as follows, where each "c" represents a hexadecimal character: {cccccccc-cccc-cccc-cccc-cccccccccccc}



#### DevicePropertyClassName

Requests the name of the device's setup class, in text format. <i>PropertyBuffer</i> points to a NULL-terminated WCHAR string. 



#### DevicePropertyCompatibleIDs

Requests the <a href="https://msdn.microsoft.com/ac439eb8-b491-4215-877d-5ee177fbdb39">compatible IDs</a> reported by the device. <i>PropertyBuffer</i> points to a REG_MULTI_SZ value.



#### DevicePropertyDeviceDescription

Requests a string describing the device, such as "Microsoft PS/2 Port Mouse", typically defined by the manufacturer. <i>PropertyBuffer</i> points to a NULL-terminated WCHAR string. 



#### DevicePropertyDriverKeyName

Requests the name of the driver-specific registry key. <i>PropertyBuffer</i> points to a NULL-terminated WCHAR string.



#### DevicePropertyEnumeratorName

Requests the name of the enumerator for the device, such as "PCI" or "root". <i>PropertyBuffer</i> points to a NULL-terminated WCHAR string.



#### DevicePropertyFriendlyName

Requests a string that can be used to distinguish between two similar devices, typically defined by the class installer. <i>PropertyBuffer</i> points to a NULL-terminated WCHAR string. 



#### DevicePropertyHardwareID

Requests the <a href="https://msdn.microsoft.com/3be5c842-d1b6-4c34-8990-e23e2d08dd23">hardware IDs</a> provided by the device that identify the device. <i>PropertyBuffer</i> points to a REG_MULTI_SZ value.



#### DevicePropertyInstallState

(Windows XP and later versions of Windows.) Requests the device's installation state. The installation state is returned as a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543130">DEVICE_INSTALL_STATE</a> enumeration value (see the Ntddk.h header file). 



#### DevicePropertyLegacyBusType

Requests the bus type, such as PCIBus or PCMCIABus. <i>PropertyBuffer</i> points to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff547839">INTERFACE_TYPE</a> enumeration value.



#### DevicePropertyLocationInformation

Requests information about the device's location on the bus; the interpretation of this information is bus-specific. <i>PropertyBuffer</i> points to a NULL-terminated WCHAR string.



#### DevicePropertyManufacturer

Requests a string identifying the manufacturer of the device. <i>PropertyBuffer</i> points to a NULL-terminated WCHAR string.



#### DevicePropertyPhysicalDeviceObjectName

Requests the name of the PDO for this device. <i>PropertyBuffer</i> points to a NULL-terminated WCHAR string.



#### DevicePropertyRemovalPolicy

(Windows XP and later versions of Windows.) Requests the device's current removal policy. The operating system uses this value as a hint to determine how the device is normally removed. The <i>PropertyBuffer</i> parameter points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543179">DEVICE_REMOVAL_POLICY</a> enumeration value.



#### DevicePropertyUINumber

Requests a number associated with the device that can be displayed in the user interface. <i>PropertyBuffer</i> points to a ULONG value.

This number is typically a user-perceived slot number, such as a number printed next to the slot on the board, or some other number that makes locating the physical device easier for the user. If the device is on a bus that has no UI number convention, or if the bus driver for the device cannot determine the UI number, this value is 0xFFFFFFFF.


### -param BufferLength [in]

Specifies the size, in bytes, of the caller-supplied <i>PropertyBuffer</i>.


### -param PropertyBuffer [out, optional]

Pointer to a caller-supplied buffer to receive the property information. The buffer can be allocated from pageable memory. The type of the buffer is determined by the <i>DeviceProperty</i> (see above).


### -param ResultLength [out]

Pointer to a ULONG to receive the size of the property information returned at <i>PropertyBuffer</i>. If <b>IoGetDeviceProperty</b> returns STATUS_BUFFER_TOO_SMALL, it sets this parameter to the required buffer length.


## -returns



<b>IoGetDeviceProperty</b> returns STATUS_SUCCESS if the call was successful. Possible error return values include the following.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The buffer at <i>PropertyBuffer</i> was too small. <i>ResultLength</i> points to the required buffer length.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_2</b></dt>
</dl>
</td>
<td width="60%">
The given <i>DeviceProperty</i> is not one of the properties handled by this routine.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
Possibly indicates that the given <i>DeviceObject</i> was not a valid PDO pointer.

</td>
</tr>
</table>
 




## -remarks



<b>IoGetDeviceProperty</b> retrieves device setup information from the registry. Use this routine, rather than accessing the registry directly, to insulate a driver from differences across platforms and from possible changes in the registry structure.

For many <i>DeviceProperty</i> requests, it can take two or more calls to <b>IoGetDeviceProperty</b> to determine the required <i>BufferLength</i>. The first call should use a best-guess value. If the return status is STATUS_BUFFER_TOO_SMALL, the driver should free its current buffer, allocate a buffer of the size returned in <i>ResultLength</i>, and call <b>IoGetDeviceProperty</b> again. Because some of the setup properties are dynamic, the data size can change between the time the required size is returned and driver calls this routine again. Therefore, drivers should call <b>IoGetDeviceProperty</b> inside a loop that runs until the return status is not STATUS_BUFFER_TOO_SMALL.

Function drivers that support devices on a legacy bus and a PnP bus can use the <b>DevicePropertyBusNumber</b>, <b>DevicePropertyBusTypeGuid</b>, and <b>DevicePropertyLegacyBusType</b> properties to distinguish between the buses.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541994">CM_RESOURCE_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543179">DEVICE_REMOVAL_POLICY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544520">ExAllocatePoolWithTag</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn922935">GUID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547839">INTERFACE_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550609">IO_RESOURCE_REQUIREMENTS_LIST</a>
 

 

