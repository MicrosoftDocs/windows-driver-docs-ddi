---
UID: NF:ntifs.IoIsOperationSynchronous
title: IoIsOperationSynchronous function (ntifs.h)
description: Learn more about the IoIsOperationSynchronous function.
tech.root: ifsk
ms.date: 09/27/2023
keywords: ["IoIsOperationSynchronous function"]
ms.keywords: IoIsOperationSynchronous, IoIsOperationSynchronous routine [Installable File System Drivers], ifsk.ioisoperationsynchronous, ioref_259181c2-f6d9-4fe6-8d4b-594e7cf8db09.xml, ntifs/IoIsOperationSynchronous
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IoIsOperationSynchronous
 - ntifs/IoIsOperationSynchronous
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoIsOperationSynchronous
---

# IoIsOperationSynchronous function

## -description

The **IoIsOperationSynchronous** routine determines whether a given IRP represents a synchronous or asynchronous I/O request.

## -parameters

### -param Irp [in]

Pointer to the IRP for the operation.

## -returns

**IoIsOperationSynchronous** returns TRUE if the operation is synchronous, otherwise FALSE.

## -remarks

**IoIsOperationSynchronous** determines whether a given IRP requests a synchronous or asynchronous I/O operation, according to the following conditions:

* If the IRP requests asynchronous paging I/O, the operation is asynchronous, even if one of the other conditions is true.

* If the IRP requests synchronous paging I/O, the operation is synchronous.

* If the file object was opened for synchronous I/O, the operation is synchronous.

* If the IRP_SYNCHRONOUS_API flag is set in the IRP, the operation is synchronous. This flag is set for operations, such as [**ZwQueryInformationFile**](nf-ntifs-ntqueryinformationfile.md) and [**ZwSetInformationFile**](nf-ntifs-ntsetinformationfile.md), that are always synchronous, even when performed on a file object that was opened for asynchronous I/O.

* If none of the above conditions is true, the operation is asynchronous.

**IoIsOperationSynchronous** also returns TRUE if the IRP contains an IOCTL or FSCTL request with an I/O or file system control code that was defined with METHOD_BUFFERED, even if the file object was opened for asynchronous I/O. Such a request is likely to be made synchronous by the file system, but this is not necessarily true in all cases.

## -see-also

[**IRP**](../wdm/ns-wdm-_irp.md)

[**IoBuildSynchronousFsdRequest**](../wdm/nf-wdm-iobuildsynchronousfsdrequest.md)

[**IoCreateFile**](../wdm/nf-wdm-iocreatefile.md)

[**IoCreateFileEx**](../ntddk/nf-ntddk-iocreatefileex.md)

[**IoCreateFileSpecifyDeviceObjectHint**](../ntddk/nf-ntddk-iocreatefilespecifydeviceobjecthint.md)

[**ZwCreateFile**](nf-ntifs-ntcreatefile.md)

[**ZwQueryInformationFile**](nf-ntifs-ntqueryinformationfile.md)

[**ZwSetInformationFile**](nf-ntifs-ntsetinformationfile.md)
