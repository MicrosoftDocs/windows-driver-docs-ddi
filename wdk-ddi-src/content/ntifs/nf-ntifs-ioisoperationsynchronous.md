---
UID: NF:ntifs.IoIsOperationSynchronous
title: IoIsOperationSynchronous function (ntifs.h)
description: The IoIsOperationSynchronous routine determines whether a given IRP represents a synchronous or asynchronous I/O request.
old-location: ifsk\ioisoperationsynchronous.htm
tech.root: ifsk
ms.assetid: b233dfab-6a99-4f2f-930e-cafd01dc4bb5
ms.date: 04/16/2018
ms.keywords: IoIsOperationSynchronous, IoIsOperationSynchronous routine [Installable File System Drivers], ifsk.ioisoperationsynchronous, ioref_259181c2-f6d9-4fe6-8d4b-594e7cf8db09.xml, ntifs/IoIsOperationSynchronous
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoIsOperationSynchronous
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoIsOperationSynchronous function


## -description


The <b>IoIsOperationSynchronous</b> routine determines whether a given IRP represents a synchronous or asynchronous I/O request. 


## -parameters




### -param Irp [in]

Pointer to the IRP for the operation. 


## -returns



<b>IoIsOperationSynchronous</b> returns <b>TRUE</b> if the operation is synchronous, otherwise <b>FALSE</b>. 




## -remarks



<b>IoIsOperationSynchronous</b> determines whether a given IRP requests a synchronous or asynchronous I/O operation, according to the following conditions: 

<ul>
<li>
If the IRP requests asynchronous paging I/O, the operation is asynchronous, even if one of the other conditions is true. 

</li>
<li>
If the IRP requests synchronous paging I/O, the operation is synchronous. 

</li>
<li>
If the file object was opened for synchronous I/O, the operation is synchronous. 

</li>
<li>
If the IRP_SYNCHRONOUS_API flag is set in the IRP, the operation is synchronous. This flag is set for operations, such as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-ntqueryinformationfile">ZwQueryInformationFile</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-ntsetinformationfile">ZwSetInformationFile</a>, that are always synchronous, even when performed on a file object that was opened for asynchronous I/O. 

</li>
<li>
If none of the above conditions is true, the operation is asynchronous. 

</li>
</ul>
<div class="alert"><b>Note</b>  <b>IoIsOperationSynchronous</b>
      also returns <b>TRUE</b> if the IRP contains an IOCTL or FSCTL request with an I/O or file system control code that was defined with METHOD_BUFFERED, even if the file object was opened for asynchronous I/O. Such a request is likely to be made synchronous by the file system, but this is not necessarily true in all cases. </div>
<div> </div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_irp">IRP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iobuildsynchronousfsdrequest">IoBuildSynchronousFsdRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iocreatefile">IoCreateFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-iocreatefileex">IoCreateFileEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-iocreatefilespecifydeviceobjecthint">IoCreateFileSpecifyDeviceObjectHint</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-ntcreatefile">ZwCreateFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-ntqueryinformationfile">ZwQueryInformationFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-ntsetinformationfile">ZwSetInformationFile</a>
 

 

