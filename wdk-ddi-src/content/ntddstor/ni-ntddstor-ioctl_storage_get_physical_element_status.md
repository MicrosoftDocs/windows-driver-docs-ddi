---
UID: NI:ntddstor.IOCTL_STORAGE_GET_PHYSICAL_ELEMENT_STATUS
title: IOCTL_STORAGE_GET_PHYSICAL_ELEMENT_STATUS
description: The IOCTL_STORAGE_GET_PHYSICAL_ELEMENT_STATUS control code queries for and returns the physical element status from a device.
old-location: storage\ioctl_storage_get_physical_element_status.htm
tech.root: storage
ms.assetid: ED46241E-1A71-447A-8D96-E81B4500E070
ms.date: 03/29/2018
ms.keywords: IOCTL_STORAGE_GET_PHYSICAL_ELEMENT_STATUS, IOCTL_STORAGE_GET_PHYSICAL_ELEMENT_STATUS control, IOCTL_STORAGE_GET_PHYSICAL_ELEMENT_STATUS control code [Storage Devices], ntddstor/IOCTL_STORAGE_GET_PHYSICAL_ELEMENT_STATUS, storage.ioctl_storage_get_physical_element_status
ms.topic: ioctl
req.header: ntddstor.h
req.include-header: WinIoctl.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
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
-	IOCTL_STORAGE_GET_PHYSICAL_ELEMENT_STATUS
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_STORAGE_GET_PHYSICAL_ELEMENT_STATUS IOCTL


## -description

The <b>IOCTL_STORAGE_GET_PHYSICAL_ELEMENT_STATUS</b> control code queries for and returns the physical element status from a device.


## -ioctlparameters




### -input-buffer

A pointer to an input buffer that receives a [**PHYSICAL_ELEMENT_STATUS_REQUEST**](ns-ntddstor-_physical_element_status_request.md) structure that defines the starting element to look for the physical element status of a device.

### -input-buffer-length

Specifies the size of the input buffer, in bytes.

### -output-buffer

A pointer to an output buffer that contains a [**PHYSICAL_ELEMENT_STATUS**](ns-ntddstor-_physical_element_status.md) structure that defines the physical element status from a device.

### -output-buffer-length

The size of the output buffer, in bytes.

### -in-out-buffer



### -inout-buffer-length


### -status-block

Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.

Otherwise, Status is set to the appropriate error condition as a NTSTATUS code. 

For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).


## -remarks

To perform this operation, call the <a href="https://msdn.microsoft.com/1d35c087-6672-4fc6-baa1-a886dd9d3878">DeviceIoControl</a> 
   function with the following parameters.

```C++
BOOL 
WINAPI 
DeviceIoControl((HANDLE)       hDevice,         // handle to device
                (DWORD)        IOCTL_STORAGE_GET_PHYSICAL_ELEMENT_STATUS, // dwIoControlCode
                (LPDWORD)      lpInBuffer,      // input buffer
                (DWORD)        nInBufferSize,   // size of input buffer
                (LPDWORD)      lpOutBuffer,     // output buffer
                (DWORD)        nOutBufferSize,  // size of output buffer
                (LPDWORD)      lpBytesReturned, // number of bytes returned
                (LPOVERLAPPED) lpOverlapped );  // OVERLAPPED structure
```

## -see-also




<a href="https://msdn.microsoft.com/1d35c087-6672-4fc6-baa1-a886dd9d3878">DeviceIoControl</a>



[**PHYSICAL_ELEMENT_STATUS**](ns-ntddstor-_physical_element_status.md)



[**PHYSICAL_ELEMENT_STATUS_REQUEST**](ns-ntddstor-_physical_element_status_request.md)
