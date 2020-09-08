---
UID: NF:ntifs.IoCheckFunctionAccess
title: IoCheckFunctionAccess function (ntifs.h)
description: Reserved for system use.
old-location: ifsk\iocheckfunctionaccess.htm
tech.root: ifsk
ms.assetid: 828a5197-eb2d-46d1-9853-0f8b4f288820
ms.date: 05/30/2019
keywords: ["IoCheckFunctionAccess function"]
ms.keywords: IoCheckFunctionAccess, IoCheckFunctionAccess function [Installable File System Drivers], ifsk.iocheckfunctionaccess, ioref_e6c92504-238b-4163-8078-35aee716744e.xml, ntifs/IoCheckFunctionAccess
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IoCheckFunctionAccess
 - ntifs/IoCheckFunctionAccess
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - IoCheckFunctionAccess
---

# IoCheckFunctionAccess function


## -description

The **IoCheckFunctionAccess** routine checks the parameters and access for a function against the current granted access to the file.

## -parameters

### -param GrantedAccess

Mask value that specifies the access currently granted to the file for the caller.

### -param MajorFunction

Major function code for the operation being performed.

### -param MinorFunction

Minor function code for the operation being performed.

### -param IoControlCode

I/O function control code for a device or file system I/O code.

### -param Arg1

Optional argument that depends on the major function. This parameter points to one of the [FILE_INFORMATION_CLASS](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_file_information_class) enum values if *MajorFunction* indicates a query or set file information function is being performed.

### -param Arg2

Optional second argument that depends on the major function. This parameter points to one of the [FS_INFORMATION_CLASS](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_fsinfoclass) enum values. This parameter must be supplied if *MajorFunction* indicates a query or set file information function is being performed.

## -returns

**IoCheckFunctionAccess** returns STATUS_SUCCESS if the caller has access to the file; otherwise, it returns STATUS_ACCESS_DENIED.

## -remarks

The *GrantedAccess* mask cannot contain any generic mappings. That is, [IoCheckDesiredAccess](nf-ntifs-iocheckdesiredaccess.md) must have been previously invoked to return a full mask.

## -see-also

[FILE_INFORMATION_CLASS](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_file_information_class)

[FS_INFORMATION_CLASS](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_fsinfoclass)

[IoCheckDesiredAccess](nf-ntifs-iocheckdesiredaccess.md)

[SeAccessCheck](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-seaccesscheck)

