---
UID: NS:fltkernel._FLT_VOLUME_PROPERTIES
title: "_FLT_VOLUME_PROPERTIES"
author: windows-driver-content
description: The FLT_VOLUME_PROPERTIES structure is passed as a parameter to FltGetVolumeProperties.
old-location: ifsk\flt_volume_properties.htm
tech.root: ifsk
ms.assetid: e7be6cb6-a59d-4244-ba36-e7d5b36b1416
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: "*PFLT_VOLUME_PROPERTIES, FLT_VOLUME_PROPERTIES, FLT_VOLUME_PROPERTIES structure [Installable File System Drivers], FltSystemStructures_9de12b81-e647-4dc7-8d4c-dd90070c7dfa.xml, PFLT_VOLUME_PROPERTIES, PFLT_VOLUME_PROPERTIES structure pointer [Installable File System Drivers], VOL_PROP_FL_DAX_VOLUME, _FLT_VOLUME_PROPERTIES, fltkernel/FLT_VOLUME_PROPERTIES, fltkernel/PFLT_VOLUME_PROPERTIES, ifsk.flt_volume_properties"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: fltkernel.h
req.include-header: Fltkernel.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	fltkernel.h
api_name:
-	FLT_VOLUME_PROPERTIES
product:
- Windows
targetos: Windows
req.typenames: FLT_VOLUME_PROPERTIES, *PFLT_VOLUME_PROPERTIES
---

# _FLT_VOLUME_PROPERTIES structure


## -description


The FLT_VOLUME_PROPERTIES structure is passed as a parameter to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543254">FltGetVolumeProperties</a>. 


## -struct-fields




### -field DeviceType

Receives the device type of the volume. Must be a valid storage device type, such as one of the following values defined in ntifs.h: 

FILE_DEVICE_CD_ROM

FILE_DEVICE_DISK

FILE_DEVICE_DVD

FILE_DEVICE_MASS_STORAGE

FILE_DEVICE_NETWORK

FILE_DEVICE_VIRTUAL_DISK

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563821">Specifying Device Types</a>. 


### -field DeviceCharacteristics

Receives the device characteristics of the volume. For more information, see the reference entry for <a href="https://msdn.microsoft.com/library/windows/hardware/ff548397">IoCreateDevice</a>. 


### -field DeviceObjectFlags

Receives the device object flags for the volume. For more information about these flags, see the reference entries for <a href="https://msdn.microsoft.com/library/windows/hardware/ff548494">IoRegisterFileSystem</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>. 


### -field AlignmentRequirement

Receives the buffer alignment required by the underlying device. The value must be one of the FILE_<i>xxxx</i>_ALIGNMENT values defined in ntifs.h. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff547807">Initializing a Device Object</a>. 


### -field SectorSize

Receives the volume sector size, in bytes. 


### -field Flags

Provides additional description of the volume. This member can be zero or one of the following flags. In versions prior to Windows 10, version 1607, this member was named <b>Reserved0</b> and reserved for system use.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="VOL_PROP_FL_DAX_VOLUME"></a><a id="vol_prop_fl_dax_volume"></a><dl>
<dt><b>VOL_PROP_FL_DAX_VOLUME</b></dt>
</dl>
</td>
<td width="60%">
This flag indicates that the volume is a direct access (DAX) volume.

</td>
</tr>
</table>
 


### -field FileSystemDriverName


<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure that receives the service name of the file system that is mounted on this volume. The buffer for this Unicode string is contiguous with this structure and does not need to be initialized before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff543254">FltGetVolumeProperties</a>. 


### -field FileSystemDeviceName

UNICODE_STRING structure that receives the name of the file system device object associated with this volume. The buffer for this Unicode string is contiguous with this structure and does not need to be initialized before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff543254">FltGetVolumeProperties</a>. 


### -field RealDeviceName

UNICODE_STRING structure that receives the name of the storage device object associated with this volume. This structure is empty for network file systems. The buffer for this Unicode string is contiguous with this structure and does not need to be initialized before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff543254">FltGetVolumeProperties</a>. 


## -remarks



Storage for the FLT_VOLUME_PROPERTIES structure is typically allocated from paged pool. 

To get the volume name for a given volume, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543249">FltGetVolumeName</a>. 

To get the volume globally unique identifier (GUID) name for a given volume, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543230">FltGetVolumeGuidName</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>



<b>FltGetVolumeName</b>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543254">FltGetVolumeProperties</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548397">IoCreateDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548494">IoRegisterFileSystem</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>
 

 

