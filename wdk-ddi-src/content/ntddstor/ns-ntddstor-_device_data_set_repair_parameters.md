---
UID: NS:ntddstor._DEVICE_DATA_SET_REPAIR_PARAMETERS
title: "_DEVICE_DATA_SET_REPAIR_PARAMETERS"
author: windows-driver-content
description: The DEVICE_DATA_SET_REPAIR_PARAMETERS structure specifies the parameters of a storage spaces repair operation specified for a data set management action.
old-location: storage\device_data_set_repair_parameters.htm
old-project: storage
ms.assetid: BBA834D0-4D21-42EF-98B0-9AF3FF28E6E2
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: "_DEVICE_DATA_SET_REPAIR_PARAMETERS, storage.device_data_set_repair_parameters, ntddstor/DEVICE_DATA_SET_REPAIR_PARAMETERS, PDEVICE_DATA_SET_REPAIR_PARAMETERS, *PDEVICE_DATA_SET_REPAIR_PARAMETERS, PDEVICE_DATA_SET_REPAIR_PARAMETERS structure pointer [Storage Devices], DEVICE_DATA_SET_REPAIR_PARAMETERS, ntddstor/PDEVICE_DATA_SET_REPAIR_PARAMETERS, DEVICE_DATA_SET_REPAIR_PARAMETERS structure [Storage Devices]"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
-	ntddstor.h
apiname:
-	DEVICE_DATA_SET_REPAIR_PARAMETERS
product: Windows
targetos: Windows
req.typenames: "*PDEVICE_DATA_SET_REPAIR_PARAMETERS, DEVICE_DATA_SET_REPAIR_PARAMETERS"
---

# _DEVICE_DATA_SET_REPAIR_PARAMETERS structure


## -description


The <b>DEVICE_DATA_SET_REPAIR_PARAMETERS</b> structure specifies the parameters of a  storage spaces  repair operation specified for a data set management action.

This parameter structure is used in a repair action for an <a href="..\ntddstor\ni-ntddstor-ioctl_storage_manage_data_set_attributes.md">IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES</a> request.  The <b>Action</b> member of the <a href="..\ntddstor\ns-ntddstor-_device_manage_data_set_attributes.md">DEVICE_MANAGE_DATA_SET_ATTRIBUTES</a> structure is set to <b>DeviceDsmAction_Repair</b>, and <b>ParameterBlockOffset</b> indicates the location of <b>DEVICE_DATA_SET_REPAIR_PARAMETERS</b>.


## -syntax


````
typedef struct _DEVICE_DATA_SET_REPAIR_PARAMETERS {
  ULONG NumberOfRepairCopies;
  ULONG SourceCopy;
  ULONG RepairCopies[ANYSIZE_ARRAY];
} DEVICE_DATA_SET_REPAIR_PARAMETERS, *PDEVICE_DATA_SET_REPAIR_PARAMETERS;
````


## -struct-fields




### -field NumberOfRepairCopies

The total  number of copies to repair.


### -field SourceCopy

The source copy number.


### -field RepairCopies

An array of copy numbers for the copies to repair.


## -remarks



The <b>ParameterBlockOffset</b> and <b>ParameterBlockLength</b> members  of <a href="..\ntddstor\ns-ntddstor-_device_manage_data_set_attributes.md">DEVICE_MANAGE_DATA_SET_ATTRIBUTES</a> are set to the location and length of the  <b>DEVICE_DATA_SET_REPAIR_PARAMETERS</b> structure in the system buffer of the <a href="..\ntddstor\ni-ntddstor-ioctl_storage_manage_data_set_attributes.md">IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES</a> request.

The <b>DataSetRangesOffset</b> and <b>DataSetRangesLength</b> members of <a href="..\ntddstor\ns-ntddstor-_device_manage_data_set_attributes.md">DEVICE_MANAGE_DATA_SET_ATTRIBUTES</a> specify the <a href="..\ntddstor\ns-ntddstor-_device_data_set_range.md">DEVICE_DATA_SET_RANGE</a> structures containing the extents of the repair copies.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552520">DEVICE_DATA_MANAGEMENT_SET_ACTION</a>



<a href="..\ntddstor\ni-ntddstor-ioctl_storage_manage_data_set_attributes.md">IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES</a>



<a href="..\ntddstor\ns-ntddstor-_device_manage_data_set_attributes.md">DEVICE_MANAGE_DATA_SET_ATTRIBUTES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DEVICE_DATA_SET_REPAIR_PARAMETERS structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

