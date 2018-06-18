---
UID: NI:ntddstor.IOCTL_STORAGE_GET_PHYSICAL_ELEMENT_STATUS
title: IOCTL_STORAGE_GET_PHYSICAL_ELEMENT_STATUS
author: windows-driver-content
description: The IOCTL_STORAGE_GET_PHYSICAL_ELEMENT_STATUS control code queries for and returns the physical element status from a device.
old-location: storage\ioctl_storage_get_physical_element_status.htm
old-project: storage
ms.assetid: ED46241E-1A71-447A-8D96-E81B4500E070
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_STORAGE_GET_PHYSICAL_ELEMENT_STATUS, IOCTL_STORAGE_GET_PHYSICAL_ELEMENT_STATUS control, IOCTL_STORAGE_GET_PHYSICAL_ELEMENT_STATUS control code [Storage Devices], ntddstor/IOCTL_STORAGE_GET_PHYSICAL_ELEMENT_STATUS, storage.ioctl_storage_get_physical_element_status
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddstor.h
req.include-header: WinIoctl.h
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


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>IOCTL_STORAGE_GET_PHYSICAL_ELEMENT_STATUS</b> 
   control code queries for and returns  the physical element status from a device.


## -ioctlparameters




### -input-buffer








### -input-buffer-length








### -output-buffer








### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block



Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.

Otherwise, Status to the appropriate error condition as a NTSTATUS code. 

For more information, see [NTSTATUS Values](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/ntstatus-values).




## -remarks



To perform this operation, call the <a href="https://msdn.microsoft.com/1d35c087-6672-4fc6-baa1-a886dd9d3878">DeviceIoControl</a> 
   function with the following parameters.


<pre class="syntax">BOOL 
   WINAPI 
   DeviceIoControl( (HANDLE)       hDevice,         // handle to device
                    (DWORD)        IOCTL_STORAGE_GET_PHYSICAL_ELEMENT_STATUS, // dwIoControlCode
                    (LPDWORD)      lpInBuffer,      // input buffer
                    (DWORD)        nInBufferSize,   // size of input buffer
                    (LPDWORD)      lpOutBuffer,     // output buffer
                    (DWORD)        nOutBufferSize,  // size of output buffer
                    (LPDWORD)      lpBytesReturned, // number of bytes returned
                    (LPOVERLAPPED) lpOverlapped );  // OVERLAPPED structure</pre>







## -see-also




<a href="https://msdn.microsoft.com/1d35c087-6672-4fc6-baa1-a886dd9d3878">DeviceIoControl</a>



<a href="https://msdn.microsoft.com/5E2AB36E-5A5C-4253-9791-A5CC157F15E3">PHYSICAL_ELEMENT_STATUS</a>



<a href="https://msdn.microsoft.com/A0876712-4D9B-4A97-8E94-AA570A71C53D">PHYSICAL_ELEMENT_STATUS_REQUEST</a>
 

 

