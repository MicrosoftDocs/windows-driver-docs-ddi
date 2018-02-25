---
UID: NF:fltkernel.FltFsControlFile
title: FltFsControlFile function
author: windows-driver-content
description: The FltFsControlFile routine sends a control code directly to a specified file system or file system filter driver, causing the corresponding driver to perform the specified action.
old-location: ifsk\fltfscontrolfile.htm
old-project: ifsk
ms.assetid: afc72cdf-ea29-4e78-95a0-fc621e3290a7
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , C, F, FltApiRef_e_to_o_3cad833f-9ece-410a-896d-1b3fe897c251.xml, FltFsControlFile, FltFsControlFile routine [Installable File System Drivers], e, fltkernel/FltFsControlFile, i, ifsk.fltfscontrolfile, l, n, o, r, s, t"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	fltmgr.sys
apiname:
-	FltFsControlFile
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltFsControlFile function


## -description


The <b>FltFsControlFile</b> routine sends a control code directly to a specified file system or file system filter driver, causing the corresponding driver to perform the specified action. 


## -syntax


````
NTSTATUS FltFsControlFile(
  _In_      PFLT_INSTANCE Instance,
  _In_      PFILE_OBJECT  FileObject,
  _In_      ULONG         FsControlCode,
  _In_opt_  PVOID         InputBuffer,
  _In_      ULONG         InputBufferLength,
  _Out_opt_ PVOID         OutputBuffer,
  _In_      ULONG         OutputBufferLength,
  _Out_opt_ PULONG        LengthReturned
);
````


## -parameters




### -param Instance [in]

Opaque instance pointer for the caller. This parameter is required and cannot be <b>NULL</b>. 


### -param FileObject [in]

File object pointer for the file or directory that is the target of this request. This parameter is required and cannot be <b>NULL</b>. 


### -param FsControlCode [in]

FSCTL_<i>XXX</i> code that indicates which file system operation is to be carried out. The value of this parameter determines the formats and required lengths of the <i>InputBuffer</i> and <i>OutputBuffer</i>, and it determines which of the following parameter pairs (<i>InputBuffer</i> and <i>InputBufferLength</i>, <i>OutputBuffer</i> and <i>OutputBufferLength</i>) is required. 


### -param InputBuffer [in, optional]

Pointer to a caller-allocated input buffer that contains device-specific information to be given to the target driver. If the <i>FsControlCode</i> parameter specifies an operation that does not require input data, this parameter is optional and can be <b>NULL</b>. 


### -param InputBufferLength [in]

Size, in bytes, of the buffer at <i>InputBuffer</i>. This value is ignored if <i>InputBuffer</i> is <b>NULL</b>. 


### -param OutputBuffer [out, optional]

Pointer to a caller-allocated output buffer in which information is returned from the target driver. If the <i>FsControlCode</i> parameter specifies an operation that does not require output data, this parameter is optional and can be <b>NULL</b>. 


### -param OutputBufferLength [in]

Size, in bytes, of the buffer at <i>OutputBuffer</i>. This value is ignored if <i>OutputBuffer</i> is <b>NULL</b>. 


### -param LengthReturned [out, optional]

Pointer to a caller-allocated variable that receives the size, in bytes, of the information returned in the buffer at <i>OutputBuffer</i>. This parameter is optional and can be <b>NULL</b>. 


## -returns



<b>FltFsControlFile</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value. 




## -remarks



Minifilter drivers should call this routine instead of <a href="..\ntifs\nf-ntifs-zwfscontrolfile.md">ZwFsControlFile</a>. 

The following FSCTL codes are currently documented for kernel-mode drivers: 


<a href="https://msdn.microsoft.com/library/windows/hardware/ff544828">FSCTL_DELETE_REPARSE_POINT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544836">FSCTL_GET_REPARSE_POINT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545462">FSCTL_OPBATCH_ACK_CLOSE_PENDING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545476">FSCTL_OPLOCK_BREAK_ACK_NO_2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545468">FSCTL_OPLOCK_BREAK_ACKNOWLEDGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545485">FSCTL_OPLOCK_BREAK_NOTIFY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545510">FSCTL_REQUEST_BATCH_OPLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545518">FSCTL_REQUEST_FILTER_OPLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545538">FSCTL_REQUEST_OPLOCK_LEVEL_1</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545546">FSCTL_REQUEST_OPLOCK_LEVEL_2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545568">FSCTL_SET_REPARSE_POINT</a>


For more information about the system-defined FSCTL_<i>XXX</i> codes, see the Remarks section of the reference entry for DeviceIoControl in the Microsoft Windows SDK documentation. 




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltdeviceiocontrolfile.md">FltDeviceIoControlFile</a>



<a href="..\ntifs\nf-ntifs-zwfscontrolfile.md">ZwFsControlFile</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltFsControlFile routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

