---
UID: NI:ntddstor.IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES
title: IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES
author: windows-driver-content
description: This IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES request is used to send a manage data set attributes request to a storage device.
old-location: storage\ioctl_storage_manage_data_set_attributes.htm
old-project: storage
ms.assetid: 678bbca6-f21f-480a-897d-a30e922d01e3
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: storage.ioctl_storage_manage_data_set_attributes, IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES control code [Storage Devices], IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES, ntddstor/IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES, k307_99edaea9-af25-4aba-ba16-0758c63252b6.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddstor.h
req.include-header: Ntddstor.h
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
req.irql: IRQL < DISPATCH_LEVEL (See Remarks section.)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddstor.h
apiname:
-	IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES
product: Windows
targetos: Windows
req.typenames: "*PSTORAGE_ZONE_CONDITION, STORAGE_ZONE_CONDITION"
---

# IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



This <b>IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES</b> request is used to send a manage data set attributes request to a storage device.




## -ioctlparameters




### -input-buffer

The buffer at <i>Irp-&gt;AssociatedIrp.SystemBuffer</i> contains a <a href="..\ntddstor\ns-ntddstor-_device_manage_data_set_attributes.md">DEVICE_MANAGE_DATA_SET_ATTRIBUTES</a> structure. Note that the buffer may include parameter and data set range blocks. Also, the <b>Action</b> member of this structure defines the action to be performed through a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552520">DEVICE_DATA_MANAGEMENT_SET_ACTION</a> enumeration value.
       


### -input-buffer-length

<i>Parameters.DeviceIoControl.InputBufferLength</i> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer, which must be at least <b>sizeof</b>(<a href="..\ntddstor\ns-ntddstor-_device_manage_data_set_attributes.md">DEVICE_MANAGE_DATA_SET_ATTRIBUTES</a>).


### -output-buffer

Depending on the value set in the <b>Action</b> member of <a href="..\ntddstor\ns-ntddstor-_device_manage_data_set_attributes.md">DEVICE_MANAGE_DATA_SET_ATTRIBUTES</a>, the request may return data in the buffer at <i>Irp-&gt;AssociatedIrp.SystemBuffer</i>. The system buffer will contain valid data if the manage data set action operation returns output and <i>Parameters.DeviceIoControl.InputBufferLength</i> &gt; 0.


### -output-buffer-length

The length of <a href="..\ntddstor\ns-ntddstor-_device_manage_data_set_attributes.md">DEVICE_MANAGE_DATA_SET_ATTRIBUTES</a>.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Status</b> field can be set to STATUS_SUCCESS, or possibly to STATUS_INVALID_DEVICE_REQUEST, STATUS_BUFFER_TOO_SMALL, STATUS_BUFFER_OVERFLOW, or some other error status.


## -remarks



Due to memory pool requirements by the storage driver stack, completion of the IRP containing this IOCTL must be at IRQL &lt; DISPATCH_LEVEL.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552520">DEVICE_DATA_MANAGEMENT_SET_ACTION</a>



<a href="..\ntddstor\ns-ntddstor-_device_manage_data_set_attributes.md">DEVICE_MANAGE_DATA_SET_ATTRIBUTES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES control code%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

