---
UID: NF:wdm.IoGetDeviceDirectory
title: IoGetDeviceDirectory function (wdm.h)
description: Returns a handle to a directory on disk specific to the specified driver object where the driver can read and write files.
ms.assetid: d0a01cd6-cf1a-4737-a8cc-770a42ff8fcb
ms.date: 10/19/2018
ms.topic: function
ms.keywords: IoGetDeviceDirectory
req.header: wdm.h
req.include-header:
req.target-type:
req.target-min-winverclnt: 
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- DllExport
api_location:
- NtosKrnl.exe
api_name: 
- IoGetDeviceDirectory
product:
- Windows
targetos: Windows

---

# IoGetDeviceDirectory function


## -description

Returns a handle to a directory on disk, in which drivers can store files. The files in that directory apply to a specific device instance.

## -parameters

### -param PhysicalDeviceObject
[_In_] A pointer to the [physical device object](ns-wdm-_device_object.md) being queried in the device stack of a particular device instance. Must not be NULL.

### -param DirectoryType
[_In_] A [**_DEVICE_DIRECTORY_TYPE**](ne-wdm-_device_directory_type.md)-type value that indicates the type of requested directory.

### -param Flags
[_In_] Must be 0.

### -param Reserved
[_In_] Reserved. Must be NULL.

### -param DeviceDirectoryHandle
[_Out_] A pointer to a variable that receives a HANDLE to the requested device directory. The caller must not pass NULL.

## -returns
Returns an appropriate [NTSTATUS value](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values). Possible values include:
| Error code               | Description                                                                                        |
| ------------------------ | -------------------------------------------------------------------------------------------------- |
| STATUS_SUCCESS           | The call successfully opened a handle to the requested device directory.                           |
| STATUS_INVALID_PARAMETER | An input value to this function is invalid. For example, _PhysicalDeviceObject_ or _DeviceDirectoryHandle_ is NULL;  _Flags_ is not 0;  _Reserved_ is not NULL. |

## -remarks
If **IoGetDeviceDirectory** is called before the required disks and volumes have been started, the function does not open a handle and returns an error. 

Drivers typically use [**ZwOpenFile**](nf-wdm-zwopenfile.md) and [**ZwCreateFile**](nf-wdm-zwcreatefile.md) to access/create files. One of the parameters for those functions is an [OBJECT_ATTRIBUTES](../wudfwdm/ns-wudfwdm-_object_attributes.md) structure, which contains the object name and a root directory. If the root directory is NULL, then the object name must be a fully qualified path. However, if you provide a handle for the root directory, then the object name must be relative to the object (in the case of files, the directory), that the handle represents. 

After the **IoGetDeviceDirectory** call succeeds, use the received HANDLE as a root directory in the [OBJECT_ATTRIBUTES](../wudfwdm/ns-wudfwdm-_object_attributes.md) that you are passing to a [**ZwOpenFile**](nf-wdm-zwopenfile.md) and [**ZwCreateFile**](nf-wdm-zwcreatefile.md).


The driver must call [**ZwClose**](nf-wdm-zwclose.md) to close the received handle when access is no longer required.

Callers of **IoGetDeviceDirectory** must be running at IRQL = PASSIVE_LEVEL in the context of a system thread.

## -see-also
[**ZwOpenFile**](nf-wdm-zwopenfile.md)

[**ZwCreateFile**](nf-wdm-zwcreatefile.md)

[**ZwClose**](nf-wdm-zwclose.md)

[**_DEVICE_DIRECTORY_TYPE**](ne-wdm-_device_directory_type.md)

[OBJECT_ATTRIBUTES](../wudfwdm/ns-wudfwdm-_object_attributes.md)

[**InitializeObjectAttributes**](../wudfwdm/nf-wudfwdm-initializeobjectattributes.md) 
