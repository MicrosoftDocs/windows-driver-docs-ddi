---
UID: NS:ntddstor._DEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT
title: "_DEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT"
author: windows-driver-content
description: The DEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT structure describes output for IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES control code requests for some data set management actions.
old-location: storage\device_manage_data_set_attributes_output.htm
old-project: storage
ms.assetid: FFC52136-8A1C-48F6-A846-C1C5BFB4570C
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PDEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT, DEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT, DEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT structure [Storage Devices], PDEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT, PDEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT structure pointer [Storage Devices], _DEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT, ntddstor/DEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT, ntddstor/PDEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT, storage.device_manage_data_set_attributes_output"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddstor.h
api_name:
-	DEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT
product: Windows
targetos: Windows
req.typenames: DEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT, *PDEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT
---

# _DEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT structure


## -description


The <b>DEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT</b> structure describes output for  <a href="..\ntddstor\ni-ntddstor-ioctl_storage_manage_data_set_attributes.md">IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES</a> control code requests for some data set management actions. 


## -syntax


````
typedef struct _DEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT {
  ULONG                             Size;
  DEVICE_DATA_MANAGEMENT_SET_ACTION Action;
  ULONG                             Flags;
  ULONG                             OperationStatus;
  ULONG                             ExtendedError;
  ULONG                             TargetDetailedError;
  ULONG                             ReservedStatus;
  ULONG                             OutputBlockOffset;
  ULONG                             OutputBlockLength;
} DEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT, *PDEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT;
````


## -struct-fields




### -field Size

The size of this structure. This is set to <b>sizeof</b>(DEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT).


### -field Action

The action related to the instance of this structure. This is a value from the <a href="..\ntddstor\ns-ntddstor-_device_manage_data_set_attributes.md">DEVICE_DATA_MANAGEMENT_SET_ACTION</a> enumeration.


### -field Flags

Flags for the data set management action. See the <b>Flags</b> member of <a href="..\ntddstor\ni-ntddstor-ioctl_storage_manage_data_set_attributes.md">IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES</a>.


### -field OperationStatus

An status resulting from the operation a performed for <b>Action</b>.


### -field ExtendedError

An extended error value originating from Windows or a driver.


### -field TargetDetailedError

An error value resulting from a failure execute the operation for <b>Action</b> at the target.


### -field ReservedStatus

Reserved.


### -field OutputBlockOffset

The position, after the beginning of this structure, where action-specific data is located.


### -field OutputBlockLength

The length of the action-specific data.


## -remarks



Depending on the value of <b>Action</b>, an output block is written at an offset of <b>OutputBlockOffset</b> after the beginning of this structure. The size of the output block is specified in <b>OutputBlockLength</b>. 

Currently, only the <b>DeviceDsmAction_Allocation</b> action uses this structure.




## -see-also

<a href="..\ntddstor\ni-ntddstor-ioctl_storage_manage_data_set_attributes.md">IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES</a>



<a href="..\ntddstor\ns-ntddstor-_device_data_set_lb_provisioning_state.md">DEVICE_DATA_SET_LB_PROVISIONING_STATE</a>



<a href="..\ntddstor\ns-ntddstor-_device_manage_data_set_attributes.md">DEVICE_DATA_MANAGEMENT_SET_ACTION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DEVICE_MANAGE_DATA_SET_ATTRIBUTES_OUTPUT structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

