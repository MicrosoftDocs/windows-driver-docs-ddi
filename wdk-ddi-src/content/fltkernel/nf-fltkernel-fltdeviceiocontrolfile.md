---
UID: NF:fltkernel.FltDeviceIoControlFile
title: FltDeviceIoControlFile function
author: windows-driver-content
description: FltDeviceIoControlFile sends a control code directly to a specified device driver, causing the corresponding driver to perform the specified action.
old-location: ifsk\fltdeviceiocontrolfile.htm
old-project: ifsk
ms.assetid: f9a6998d-f340-47ad-a9be-ff7ef76c627e
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FltDeviceIoControlFile function [Installable File System Drivers], FltDeviceIoControlFile, ifsk.fltdeviceiocontrolfile, FltApiRef_a_to_d_0e8f1a72-1620-4d72-8569-7411c724e906.xml, fltkernel/FltDeviceIoControlFile
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	FltMgr.lib
-	FltMgr.dll
apiname:
-	FltDeviceIoControlFile
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltDeviceIoControlFile function


## -description


<b>FltDeviceIoControlFile</b> sends a control code directly to a specified device driver, causing the corresponding driver to perform the specified action. 


## -syntax


````
NTSTATUS FltDeviceIoControlFile(
  _In_      PFLT_INSTANCE Instance,
  _In_      PFILE_OBJECT  FileObject,
  _In_      ULONG         IoControlCode,
  _In_opt_  PVOID         InputBuffer,
  _In_      ULONG         InputBufferLength,
  _Out_     PVOID         OutputBuffer,
  _In_      ULONG         OutputBufferLength,
  _Out_opt_ PULONG        LengthReturned
);
````


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

<a href="..\fltkernel\nf-fltkernel-fltfscontrolfile.md">FltFsControlFile</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltDeviceIoControlFile function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

