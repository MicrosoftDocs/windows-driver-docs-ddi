---
UID: NF:fltkernel.FltFsControlFile
title: FltFsControlFile function
author: windows-driver-content
description: The FltFsControlFile routine sends a control code directly to a specified file system or file system filter driver, causing the corresponding driver to perform the specified action.
old-location: ifsk\fltfscontrolfile.htm
old-project: ifsk
ms.assetid: afc72cdf-ea29-4e78-95a0-fc621e3290a7
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FltApiRef_e_to_o_3cad833f-9ece-410a-896d-1b3fe897c251.xml, FltFsControlFile, FltFsControlFile routine [Installable File System Drivers], fltkernel/FltFsControlFile, ifsk.fltfscontrolfile
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltFsControlFile
product:
- Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltFsControlFile function


## -description


The <b>FltFsControlFile</b> routine sends a control code directly to a specified file system or file system filter driver, causing the corresponding driver to perform the specified action. 


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



Minifilter drivers should call this routine instead of <a href="https://msdn.microsoft.com/library/windows/hardware/ff566462">ZwFsControlFile</a>. 

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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542046">FltDeviceIoControlFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566462">ZwFsControlFile</a>
 

 

