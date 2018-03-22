---
UID: NF:wdm.IoGetDriverDirectory
title: IoGetDriverDirectory function
author: windows-driver-content
description: TBD
ms.assetid: ff2a6c2a-e402-4e8a-920a-c9baa9aa237e
ms.author: windowsdriverdev
ms.date: 
ms.topic: function
ms.keywords: IoGetDriverDirectory
req.header: wdm.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1803
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
-	IoGetDriverDirectory
product: Windows
targetos: Windows

---

# IoGetDriverDirectory function


## -description

Returns a handle to a directory on disk, to the specified driver object, from which the driver can read and write files.

## -parameters

### -param DriverObject
[_In_] A pointer to the driver object ([**DRIVER_OBJECT**](ns-wdm-_driver_object.md) structure) of the calling driver.

### -param DirectoryType
[_In_] A [**_DRIVER_DIRECTORY_TYPE**](ne-wdm-_driver_directory_type.md)-type value that indicates the type of requested directory.

### -param Flags
[_In_] Must be 0, otherwise this function returns STATUS_INVALID_PARAMETER.

### -param DriverDirectoryHandle
[_Out_] A pointer to a variable that receives a HANDLE to the requested driver directory. The caller must not pass NULL, otherwise this function returns STATUS_INVALID_PARAMETER.

## -returns
Returns STATUS_SUCCESS if the call successfully opened a handle to the requested driver directory. Otherwise returns an appropriate [NTSTATUS value](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/ntstatus-values). 

## -remarks
If **IoGetDriverDirectory** is called before the required disks and volumes have been started, the function does not open a handle and returns an error. 

The driver must call [**ZwClose**](..\ntifs\nf-ntifs-ntclose.md) to close the received handle when access is no longer required.

Callers of **IoGetDriverDirectory** must be running at IRQL = PASSIVE_LEVEL in the context of a system thread.


## -see-also
[**DRIVER_OBJECT**](ns-wdm-_driver_object.md) 

[**_DRIVER_DIRECTORY_TYPE**](ne-wdm-_driver_directory_type.md)

[**ZwClose**](..\ntifs\nf-ntifs-ntclose.md)