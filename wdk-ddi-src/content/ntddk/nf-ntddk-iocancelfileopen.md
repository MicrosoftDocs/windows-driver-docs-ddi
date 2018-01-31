---
UID: NF:ntddk.IoCancelFileOpen
title: IoCancelFileOpen function
author: windows-driver-content
description: The IoCancelFileOpen routine can be used by a file system filter driver to close a file that has been opened by a file system driver in the filter driver's device stack.
old-location: ifsk\iocancelfileopen.htm
old-project: ifsk
ms.assetid: 249a77b4-c0da-4445-a669-1c4e2ced5b57
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: IoCancelFileOpen, ntddk/IoCancelFileOpen, ioref_e63977d2-a70b-4743-85e2-557458ca89ae.xml, IoCancelFileOpen routine [Installable File System Drivers], ifsk.iocancelfileopen
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows 2000 and later.
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoCancelFileOpen
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# IoCancelFileOpen function


## -description


The <b>IoCancelFileOpen</b> routine can be used by a file system filter driver to close a file that has been opened by a file system driver in the filter driver's device stack.


## -syntax


````
VOID IoCancelFileOpen(
  _In_ PDEVICE_OBJECT DeviceObject,
  _In_ PFILE_OBJECT   FileObject
);
````


## -parameters




#### - DeviceObject [in]

Pointer to the top of the device stack immediately below the filter driver's device object.


#### - FileObject [in]

Pointer to the file object for the file to be closed.


## -returns


None



## -remarks


If a file system filter driver determines that a file-open or file-create request must fail after the lower-level drivers have already completed the request with STATUS_SUCCESS, it can use <b>IoCancelFileOpen</b> to close the file opened by the lower-level drivers.
<div class="alert"><b>Note</b>    Although STATUS_REPARSE is a success NTSTATUS value, it is not necessary to call <b>IoCancelFileOpen</b> for a create operation that was completed with STATUS_REPARSE, because this status value indicates that the file was not successfully opened. </div><div> </div>A successful call to <b>IoCancelFileOpen</b> has the following effect: To minifilters and legacy filters that are above the caller in the file system stack, the create request appears to have failed. To those that are below the caller, the file appears to have been opened (or created) and then closed. 

Note that <b>IoCancelFileOpen</b> does not undo any modifications to the file. For example, <b>IoCancelFileOpen</b> does not delete a newly created file or restore a file that was overwritten or superseded to its previous state. 

A typical example is as follows:
<ul>
<li>
A filter driver exists between a higher-level filter driver and a lower-level file system driver.

</li>
<li>
The filter driver passes an IRP_MJ_CREATE request down the device stack to the file system driver, and the file system driver completes the IRP_MJ_CREATE request with status STATUS_SUCCESS.

</li>
<li>
Before the filter driver completes the create request, it determines that the file must be closed.

</li>
<li>
The filter driver uses <b>IoCancelFileOpen</b> to close the file that was opened by the file system driver. 

</li>
</ul>After calling <b>IoCancelFileOpen</b>, the filter driver should complete the create request with an appropriate error code such as STATUS_UNSUCCESSFUL or STATUS_ACCESS_DENIED. In addition, it should set the <b>Irp-&gt;IoStatus.Information</b> field to zero. 

<b>IoCancelFileOpen</b> must be called before any handles are created for the file. Callers can check the <b>Flags</b> member of the <a href="..\wdm\ns-wdm-_file_object.md">FILE_OBJECT</a> structure that the <i>FileObject</i> parameter points to. If the FO_HANDLE_CREATED flag is set, this means that one or more handles have been created for the file, so it is not safe to call <b>IoCancelFileOpen</b>. 

<b>IoCancelFileOpen</b> sets the FO_FILE_OPEN_CANCELLED flag in the <b>Flags</b> member of the file object that <i>FileObject</i> points to. This flag indicates that the IRP_MJ_CREATE request has been canceled, and an IRP_MJ_CLOSE request will be issued for this file object. Once the create operation has been canceled, it cannot be reissued - that is, STATUS_REPARSE cannot be returned by the legacy filter driver if it has called the <b>IoCreateFileOpen</b> routine.

Minifilters should use <a href="..\fltkernel\nf-fltkernel-fltcancelfileopen.md">FltCancelFileOpen</a> instead of <b>IoCancelFileOpen</b>. 



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a>

<a href="..\wdm\nf-wdm-zwcreatefile.md">ZwCreateFile</a>

<a href="..\ntddk\nf-ntddk-iocreatefilespecifydeviceobjecthint.md">IoCreateFileSpecifyDeviceObjectHint</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550720">IRP_MJ_CLOSE</a>

<a href="..\fltkernel\nf-fltkernel-fltcancelfileopen.md">FltCancelFileOpen</a>

<a href="..\fltkernel\nf-fltkernel-fltreissuesynchronousio.md">FltReissueSynchronousIo</a>

<a href="..\wdm\nf-wdm-iocreatefile.md">IoCreateFile</a>

<a href="..\wdm\nf-wdm-zwopenfile.md">ZwOpenFile</a>

<a href="..\ntddk\nf-ntddk-iocreatefileex.md">IoCreateFileEx</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20IoCancelFileOpen routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

