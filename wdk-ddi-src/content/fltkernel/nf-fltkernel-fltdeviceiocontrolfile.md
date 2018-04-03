---
UID: NF:fltkernel.FltDeviceIoControlFile
title: FltDeviceIoControlFile function
author: windows-driver-content
description: FltDeviceIoControlFile sends a control code directly to a specified device driver, causing the corresponding driver to perform the specified action.
old-location: ifsk\fltdeviceiocontrolfile.htm
old-project: ifsk
ms.assetid: f9a6998d-f340-47ad-a9be-ff7ef76c627e
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FltApiRef_a_to_d_0e8f1a72-1620-4d72-8569-7411c724e906.xml, FltDeviceIoControlFile, FltDeviceIoControlFile function [Installable File System Drivers], fltkernel/FltDeviceIoControlFile, ifsk.fltdeviceiocontrolfile
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
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	FltMgr.lib
-	FltMgr.dll
api_name:
-	FltDeviceIoControlFile
product:
- Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltDeviceIoControlFile function


## -description


<b>FltDeviceIoControlFile</b> sends a control code directly to a specified device driver, causing the corresponding driver to perform the specified action. 


## -parameters




### -param Instance [in]

Opaque instance pointer for the caller. This parameter is required and cannot be <b>NULL</b>. 


### -param FileObject [in]

File object pointer for the file or device that is the target of this request. This parameter is required and cannot be <b>NULL</b>. 


### -param IoControlCode [in]

IOCTL_<i>XXX</i> code that indicates which device I/O operation is to be carried out. The value of this parameter determines the formats and required lengths of the <i>InputBuffer</i> and <i>OutputBuffer</i>, and it determines which of the following parameter pairs (<i>InputBuffer</i> and <i>InputBufferLength</i>, or <i>OutputBuffer</i> and <i>OutputBufferLength</i>) is required. 


### -param InputBuffer [in, optional]

Pointer to a caller-allocated input buffer that contains device-specific information to be given to the target driver. If the <i>IoControlCode</i> parameter specifies an operation that does not require input data, this parameter is optional and can be <b>NULL</b>. 


### -param InputBufferLength [in]

Size, in bytes, of the buffer at <i>InputBuffer</i>. This value is ignored if <i>InputBuffer</i> is <b>NULL</b>. 


### -param OutputBuffer [out]

Pointer to a caller-allocated output buffer in which information is returned from the target driver. If the <i>IoControlCode</i> parameter specifies an operation that does not require output data, this parameter is optional and can be <b>NULL</b>. 


### -param OutputBufferLength [in]

Size, in bytes, of the buffer at <i>OutputBuffer</i>. This value is ignored if <i>OutputBuffer</i> is <b>NULL</b>. 


### -param LengthReturned [out, optional]

Pointer to a caller-allocated variable that receives the size, in bytes, of the information returned in the buffer at <i>OutputBuffer</i>. This parameter is optional and can be <b>NULL</b>. 


## -returns



<b>FltDeviceIoControlFile</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value. 




## -remarks



For more information about the system-defined IOCTL_<i>XXX</i> codes, see the Remarks section of the reference entry for <b>DeviceIoControl</b> in the Microsoft Windows SDK documentation. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542988">FltFsControlFile</a>
 

 

