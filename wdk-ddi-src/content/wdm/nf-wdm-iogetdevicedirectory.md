---
UID: NF:wdm.IoGetDeviceDirectory
title: IoGetDeviceDirectory function
author: windows-driver-content
description: Returns a handle to a directory on disk specific to the specified driver object where the driver can read and write files.
ms.assetid: d0a01cd6-cf1a-4737-a8cc-770a42ff8fcb
ms.author: windowsdriverdev
ms.date: 
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
topictype: 
-	apiref
apitype: 
-	DllExport
apilocation: 
-	NtosKrnl.exe
apiname: 
-	IoGetDeviceDirectory
product: Windows
targetos: Windows

---

# IoGetDeviceDirectory function


## -description

Returns a handle to a directory on disk, in which the drivers can store files. The files in that directory apply to a specific device node.

## -parameters

### -param PhysicalDeviceObject
[_In_] A pointer to the [physical device object](ns-wdm-_device_object.md) in the device node of a particular device instance. Must not be NULL.

### -param DirectoryType
[_In_] A [**_DEVICE_DIRECTORY_TYPE**](ne-wdm-_device_directory_type.md)-type value that indicates the type of requested directory.

### -param Flags
[_In_] Must be 0.

### -param Reserved
[_In_] Reserved. Must be NULL.

### -param DeviceDirectoryHandle
[_Out_] A pointer to a variable that receives a HANDLE to the requested device directory. The caller must not pass NULL.

## -returns
Returns an appropriate [NTSTATUS value](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/ntstatus-values). Possible values include:
| Error code               | Description                                                                                        |
| ------------------------ | -------------------------------------------------------------------------------------------------- |
| STATUS_SUCCESS           | The call successfully opened a handle to the requested driver directory.                           |
| STATUS_INVALID_PARAMETER | _PhysicalDeviceObject_ or DeviceDirectoryHandle is NULL;  _Flags_ is not 0;  Reserved is not NULL. |

## -remarks
If **IoGetDeviceDirectory** is called before the required disks and volumes have been started, the function does not open a handle and returns an error. 

The driver must call [**ZwClose**](..\ntifs\nf-ntifs-ntclose.md) to close the received handle when access is no longer required.

Callers of **IoGetDeviceDirectory** must be running at IRQL = PASSIVE_LEVEL in the context of a system thread.

## -see-also
[**ZwClose**](..\ntifs\nf-ntifs-ntclose.md)

[**_DEVICE_DIRECTORY_TYPE**](ne-wdm-_device_directory_type.md)