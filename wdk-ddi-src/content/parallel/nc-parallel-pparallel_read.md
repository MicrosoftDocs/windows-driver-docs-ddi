---
UID: NC:parallel.PPARALLEL_READ
title: PPARALLEL_READ (parallel.h)
description: The PPARALLEL_READ-typed callback routine reads data from a parallel device. The system-supplied bus driver for parallel ports supplies this routine.
old-location: parports\pparallel_read.htm
tech.root: parports
ms.assetid: a478fd0d-3fbe-4cd9-aaf9-67b74b607770
ms.date: 02/15/2018
keywords: ["PPARALLEL_READ callback"]
ms.keywords: PPARALLEL_READ, PPARALLEL_READ function pointer [Parallel Ports], cisspd_ae27b566-d561-4bc8-9519-fc3c35069791.xml, parallel/PPARALLEL_READ, parports.pparallel_read
f1_keywords:
 - "parallel/PPARALLEL_READ"
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
- PPARALLEL_READ
product:
- Windows
targetos: Windows
req.typenames: RILGBATOKEN, *LPRILGBATOKEN
---

# PPARALLEL_READ callback


## -description


The PPARALLEL_READ-typed callback routine reads data from a parallel device. The system-supplied bus driver for parallel ports supplies this routine.


## -prototype


```cpp
typedef NTSTATUS ( *PPARALLEL_READ)(
  _In_  PVOID  Context,
  _Out_ PVOID  Buffer,
  _In_  ULONG  NumBytesToRead,
  _Out_ PULONG NumBytesRead,
  _In_  UCHAR  Channel
);
```


## -parameters




### -param Context [in]

Pointer to the device extension of a parallel device's physical device object (<a href="https://docs.microsoft.com/windows-hardware/drivers/">PDO</a>).


### -param Buffer [out]

Pointer to a read buffer that the caller allocates.


### -param NumBytesToRead [in]

Specifies the number of bytes to read. Must less than or equal to the number of bytes in the caller-allocated read buffer.


### -param NumBytesRead [out]

Specifies the number of bytes that were actually read from the parallel device and saved in the caller-allocated read buffer.


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
The requested data was successfully transferred from the device.

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



To obtain a pointer to the system-supplied PPARALLEL_READ callback, a kernel-mode driver uses an <a href="..\parallel\ni-parallel-ioctl_internal_parclass_connect.md">IOCTL_INTERNAL_PARCLASS_CONNECT</a> request, which returns a <a href="..\parallel\ns-parallel-_parclass_information.md">PARCLASS_INFORMATION</a> structure. The <b>ParallelRead</b> member of the PARCLASS_INFORMATION structure is a pointer to this callback.

A client can only use this routine if it has a lock on a parallel port. A client obtains a lock on a parallel port by using an <a href="..\parallel\ni-parallel-ioctl_internal_lock_port.md">IOCTL_INTERNAL_LOCK_PORT</a> request.

The PPARALLEL_READ callback runs in the caller's thread at the IRQL of the caller.




## -see-also

<a href="..\parallel\nc-parallel-pparallel_write.md">PPARALLEL_WRITE</a>



<a href="..\parallel\ni-parallel-ioctl_internal_lock_port.md">IOCTL_INTERNAL_LOCK_PORT</a>



 

 


