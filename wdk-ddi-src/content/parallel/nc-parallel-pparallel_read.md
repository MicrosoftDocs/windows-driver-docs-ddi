---
UID: NC:parallel.PPARALLEL_READ
title: PPARALLEL_READ
author: windows-driver-content
description: The PPARALLEL_READ-typed callback routine reads data from a parallel device. The system-supplied bus driver for parallel ports supplies this routine.
old-location: parports\pparallel_read.htm
old-project: parports
ms.assetid: a478fd0d-3fbe-4cd9-aaf9-67b74b607770
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: parports.pparallel_read, PPARALLEL_READ function pointer [Parallel Ports], PPARALLEL_READ, parallel/PPARALLEL_READ, cisspd_ae27b566-d561-4bc8-9519-fc3c35069791.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	parallel.h
apiname:
-	PPARALLEL_READ
product: Windows
targetos: Windows
req.typenames: "*LPRILGBATOKEN, RILGBATOKEN"
---

# PPARALLEL_READ callback


## -description


The PPARALLEL_READ-typed callback routine reads data from a parallel device. The system-supplied bus driver for parallel ports supplies this routine.


## -prototype


````
typedef NTSTATUS ( *PPARALLEL_READ)(
  _In_  PVOID  Context,
  _Out_ PVOID  Buffer,
  _In_  ULONG  NumBytesToRead,
  _Out_ PULONG NumBytesRead,
  _In_  UCHAR  Channel
);
````


## -parameters




### -param Context [in]

Pointer to the device extension of a parallel device's physical device object (<a href="https://msdn.microsoft.com/139a10e9-203b-499b-9291-8537eae9189c">PDO</a>).


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

<a href="..\parallel\ni-parallel-ioctl_internal_lock_port.md">IOCTL_INTERNAL_LOCK_PORT</a>



<a href="..\parallel\nc-parallel-pparallel_write.md">PPARALLEL_WRITE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [parports\parports]:%20PPARALLEL_READ function pointer%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

