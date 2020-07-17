---
UID: NC:parallel.PPARALLEL_WRITE
title: PPARALLEL_WRITE (parallel.h)
description: The PPARALLEL_WRITE-typed callback routine writes data to a parallel device. The system-supplied bus driver for parallel ports supplies this routine.
old-location: parports\pparallel_write.htm
tech.root: parports
ms.assetid: 4973b1e2-5828-40d1-bb2e-da67a406eafa
ms.date: 02/15/2018
keywords: ["PPARALLEL_WRITE callback"]
ms.keywords: PPARALLEL_WRITE, PPARALLEL_WRITE function pointer [Parallel Ports], cisspd_c9bcb3ed-ca6a-44d7-8952-f96f76490262.xml, parallel/PPARALLEL_WRITE, parports.pparallel_write
f1_keywords:
 - "parallel/PPARALLEL_WRITE"
 - "PPARALLEL_WRITE"
req.header: parallel.h
req.include-header: Parallel.h
req.target-type: Desktop
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- parallel.h
api_name:
- PPARALLEL_WRITE
product:
- Windows
targetos: Windows
req.typenames: RILGBATOKEN, *LPRILGBATOKEN
---

# PPARALLEL_WRITE callback


## -description


The PPARALLEL_WRITE-typed callback routine writes data to a parallel device. The system-supplied bus driver for parallel ports supplies this routine.


## -prototype


```cpp
typedef NTSTATUS ( *PPARALLEL_WRITE)(
  _In_  PVOID  Context,
  _In_  PVOID  Buffer,
  _In_  ULONG  NumBytesToWrite,
  _Out_ PULONG NumBytesWritten,
  _In_  UCHAR  Channel
);
```


## -parameters




### -param Context [in]

Pointer to the device extension of a parallel device's physical device object (<a href="https://docs.microsoft.com/windows-hardware/drivers/">PDO</a>).


### -param Buffer [in]

Pointer to a caller-allocated write buffer.


### -param NumBytesToWrite [in]

Specifies the number of bytes to copy from the write buffer to the parallel device. Must be less than or equal to the number of bytes in the caller-allocated write buffer.


### -param NumBytesWritten [out]

Specifies the number of bytes that were actually copied from the caller-allocated write buffer to the parallel device.


### -param Channel [in]

Not used.


## -returns



<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The caller-supplied data was successfully transferred to the device.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_<i>Xxx</i></b></dt>
</dl>
</td>
<td width="60%">
An internal operation resulted in an NTSTATUS error.

</td>
</tr>
</table>
 




## -remarks



To obtain a pointer to the system-supplied PPARALLEL_WRITE callback, a kernel-mode driver uses an <a href="..\parallel\ni-parallel-ioctl_internal_parclass_connect.md">IOCTL_INTERNAL_PARCLASS_CONNECT</a> request, which returns a <a href="..\parallel\ns-parallel-_parclass_information.md">PARCLASS_INFORMATION</a> structure. The <b>ParallelWrite</b> member of the PARCLASS_INFORMATION structure is a pointer to this callback.

A client can only use this routine if it has a lock on a parallel port. A client obtains a lock on a parallel port by using an <a href="..\parallel\ni-parallel-ioctl_internal_lock_port.md">IOCTL_INTERNAL_LOCK_PORT</a> request.

The PPARALLEL_WRITE callback runs in the caller's thread at the IRQL of the caller.




## -see-also

<a href="..\parallel\nc-parallel-pparallel_read.md">PPARALLEL_READ</a>



<a href="..\parallel\ni-parallel-ioctl_internal_lock_port.md">IOCTL_INTERNAL_LOCK_PORT</a>



 

 


