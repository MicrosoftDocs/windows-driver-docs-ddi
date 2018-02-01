---
UID: NI:ntddstor.IOCTL_STORAGE_QUERY_PROPERTY
title: IOCTL_STORAGE_QUERY_PROPERTY
author: windows-driver-content
description: A driver can use IOCTL_STORAGE_QUERY_PROPERTY to return properties of a storage device or adapter.
old-location: storage\ioctl_storage_query_property.htm
old-project: storage
ms.assetid: b68c5971-6d09-49a8-873d-8736068f6003
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.ioctl_storage_query_property, IOCTL_STORAGE_QUERY_PROPERTY control code [Storage Devices], IOCTL_STORAGE_QUERY_PROPERTY, ntddstor/IOCTL_STORAGE_QUERY_PROPERTY, k307_1ee2fd05-4e88-47ef-8ed5-0553bcccc0d7.xml
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddstor.h
apiname:
-	IOCTL_STORAGE_QUERY_PROPERTY
product: Windows
targetos: Windows
req.typenames: STORAGE_ZONE_CONDITION, *PSTORAGE_ZONE_CONDITION
---

# IOCTL_STORAGE_QUERY_PROPERTY IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



A driver can use <b>IOCTL_STORAGE_QUERY_PROPERTY</b> to return properties of a storage device or adapter. The request indicates the kind of information to retrieve, such as inquiry data for a device or capabilities and limitations of an adapter. <b>IOCTL_STORAGE_QUERY_PROPERTY</b> can also be used to determine whether the port driver supports a particular property or which fields in the property descriptor can be modified with a subsequent change-property request. 




## -ioctlparameters




### -input-buffer

<b>
       Parameters.DeviceIoControl.InputBufferLength</b> indicates the size, in bytes, of the parameter buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>, which must be &gt;= <b>sizeof</b>(<a href="..\ntddstor\ns-ntddstor-_storage_property_query.md">STORAGE_PROPERTY_QUERY</a>).

<b>
       Irp-&gt;AssociatedIrp.SystemBuffer</b> contains <a href="..\ntddstor\ns-ntddstor-_storage_property_query.md">STORAGE_PROPERTY_QUERY</a> data that specifies whether to query the device or the adapter, the type of query to perform, and any additional parameters required for the query, such as the page code for a particular SCSI mode sense page. Device properties must be retrieved only from a device; attempting to retrieve device properties from an adapter will cause an error. 

<b>
       Parameters.DeviceIoControl.OutputBufferLength</b> indicates the number of bytes that can be written to <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. <b>OutputBufferLength</b> can be zero to determine whether a property exists without retrieving its data. 


### -input-buffer-length

<b>
       Parameters.DeviceIoControl.InputBufferLength</b> indicates the size, in bytes, of the parameter buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>, which must be &gt;= <b>sizeof</b>(<a href="..\ntddstor\ns-ntddstor-_storage_property_query.md">STORAGE_PROPERTY_QUERY</a>).


### -output-buffer

The driver returns query data to the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. Varying amounts of bus-specific data can be appended to the structure. 


### -output-buffer-length

Cast the structure returned to a <a href="..\ntddstor\ns-ntddstor-_storage_descriptor_header.md">STORAGE_DESCRIPTOR_HEADER</a> and check its <b>Size</b> member to determine the number of bytes the structure actually requires.


### -in-out-buffer


<text></text>



### -inout-buffer-length


<text></text>



### -status-block

The <b>Information</b> field is set to the number of bytes returned. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INVALID_DEVICE_REQUEST, STATUS_INVALID_PARAMETER, or STATUS_NOT_SUPPORTED. 


## -see-also

<a href="..\ntddstor\ns-ntddstor-_storage_descriptor_header.md">STORAGE_DESCRIPTOR_HEADER</a>

<a href="..\ntddstor\ns-ntddstor-_storage_property_query.md">STORAGE_PROPERTY_QUERY</a>

<a href="https://msdn.microsoft.com/198E7A54-5AE3-4C6E-9E66-17818B999599">STORAGE_RPMB_DATA_FRAME</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_STORAGE_QUERY_PROPERTY control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

