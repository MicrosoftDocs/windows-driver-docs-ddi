---
UID: NS:ntddstor._DEVICE_DSM_NOTIFICATION_PARAMETERS
title: "_DEVICE_DSM_NOTIFICATION_PARAMETERS"
author: windows-driver-content
description: The DEVICE_DSM_NOTIFICATION_PARAMETERS structure specifies the parameters for a notification action related to the data-set attributes for a device.
old-location: storage\device_dsm_notification_parameters.htm
tech.root: storage
ms.assetid: 57885E58-C7EC-493E-9AB8-B9DABC6CEA2A
ms.date: 3/29/2018
ms.keywords: "*PDEVICE_DSM_NOTIFICATION_PARAMETERS, DEVICE_DSM_NOTIFICATION_PARAMETERS, DEVICE_DSM_NOTIFICATION_PARAMETERS structure [Storage Devices], PDEVICE_DSM_NOTIFICATION_PARAMETERS, PDEVICE_DSM_NOTIFICATION_PARAMETERS structure pointer [Storage Devices], _DEVICE_DSM_NOTIFICATION_PARAMETERS, ntddstor/DEVICE_DSM_NOTIFICATION_PARAMETERS, ntddstor/PDEVICE_DSM_NOTIFICATION_PARAMETERS, storage.device_dsm_notification_parameters"
ms.topic: struct
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: Windows 7
req.target-min-winversvr: Windows Server 2008 R2
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
-	Ntddstor.h
api_name:
-	DEVICE_DSM_NOTIFICATION_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: DEVICE_DSM_NOTIFICATION_PARAMETERS, *PDEVICE_DSM_NOTIFICATION_PARAMETERS
---

# _DEVICE_DSM_NOTIFICATION_PARAMETERS structure


## -description


The <b>DEVICE_DSM_NOTIFICATION_PARAMETERS</b> structure specifies the parameters for a notification action related to the data-set attributes for a device. 

The notification  action is specified in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552527">DEVICE_MANAGE_DATA_SET_ATTRIBUTES</a> structure that is contained in the system buffer of an <a href="https://msdn.microsoft.com/library/windows/hardware/ff560573">IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES</a> request.


## -struct-fields




### -field Size

Specifies the total size, in bytes, of this structure. The value of this member must include the total size, in bytes, of the <b>FileTypeIDs</b> member.


### -field Flags

A flag that specifies the characteristics of the notification operation. The  <b>Flags</b> member must be set to one of the following values:





#### DEVICE_DSM_NOTIFY_FLAG_BEGIN

The Logical Block Address (LBA) range is currently being used by the file types that are specified in the <b>FileTypeIDs</b> member. 

<div class="alert"><b>Note</b>  The LBA range is specified by the data set range of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552527">DEVICE_MANAGE_DATA_SET_ATTRIBUTES</a> structure.</div>
<div> </div>


#### DEVICE_DSM_NOTIFY_FLAG_END

The LBA range is no longer being used by the file types that are specified in the <b>FileTypeIDs</b> member. 


### -field NumFileTypeIDs

The number of entries in the <b>FileTypeIDs</b> member.


### -field FileTypeID

 




#### - FileTypeIDs

One or more <a href="https://msdn.microsoft.com/library/windows/hardware/dn922935">GUID</a> values that specify the file type for the notification operation. The following table describes the <b>FileTypeIDs</b> GUID values.

<table>
<tr>
<th>GUID value</th>
<th>Description</th>
</tr>
<tr>
<td>FILE_TYPE_NOTIFICATION_GUID_PAGE_FILE</td>
<td>Specifies a notification operation for a page file.</td>
</tr>
<tr>
<td>FILE_TYPE_NOTIFICATION_GUID_HIBERNATION_FILE</td>
<td>Specifies a notification operation for the system hibernation file.</td>
</tr>
<tr>
<td>FILE_TYPE_NOTIFICATION_GUID_CRASHDUMP_FILE</td>
<td>Specifies a notification operation for a system crash dump file.</td>
</tr>
</table>
 


## -remarks



Starting with Windows 7, the NTFS file system notifies the storage stack when the LBA data set range changes for  a specified set of files. The file system issues this notification by sending the storage stack an <a href="https://msdn.microsoft.com/library/windows/hardware/ff560573">IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES</a> request with a system buffer that contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552527">DEVICE_MANAGE_DATA_SET_ATTRIBUTES</a> structure. For the notification operation, the file system sets the members of the <b>DEVICE_MANAGE_DATA_SET_ATTRIBUTES</b> structure as follows:

<ul>
<li>
The <b>Action</b> member is set to <b>DeviceDsmAction_Notification</b>.

</li>
<li>
The <b>ParameterBlockOffset</b> and <b>ParameterBlockLength</b> members specify the location and size of the parameter block for the notification operation. The parameter block is formatted as a <b>DEVICE_DSM_NOTIFICATION_PARAMETERS</b> structure.

</li>
<li>
If the <b>Flags</b> member is set to zero, the <b>DataSetRangesOffset</b> and <b>DataSetRangesLength</b> members specify the data set range block within the IOCTL payload.

If the <b>Flags</b> member is set to <b>DEVICE_DSM_FLAG_ENTIRE_DATA_SET_RANGE</b>, the <b>DataSetRangesOffset</b> and <b>DataSetRangesLength</b> members are set to zero and the notification action includes the entire data set range for the specified files.

</li>
</ul>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552527">DEVICE_MANAGE_DATA_SET_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560573">IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES</a>
 

 

