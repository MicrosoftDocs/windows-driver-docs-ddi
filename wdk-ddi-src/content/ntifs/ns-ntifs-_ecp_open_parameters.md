---
UID: NS:ntifs._ECP_OPEN_PARAMETERS
title: ECP_OPEN_PARAMETERS (ntifs.h)
description: The ECP_OPEN_PARAMETERS structure allows a caller to specify the purpose of opening of a file without interfering with existing handles and/or oplocks on the file.
old-location: ifsk\ecp_open_parameters.htm
tech.root: ifsk
ms.assetid: 1223C77A-EAEC-4FCF-B2CC-F1E2935AF5CB
ms.date: 12/15/2019
ms.keywords: "*PECP_OPEN_PARAMETERS, ECP_OPEN_PARAMETERS, ECP_OPEN_PARAMETERS structure [Installable File System Drivers], PECP_OPEN_PARAMETERS, PECP_OPEN_PARAMETERS structure pointer [Installable File System Drivers], _ECP_OPEN_PARAMETERS, ifsk.ecp_open_parameters, ntifs/ECP_OPEN_PARAMETERS, ntifs/PECP_OPEN_PARAMETERS"
f1_keywords:
 - "ntifs/ECP_OPEN_PARAMETERS"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 10, version 1709.
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
- HeaderDef
api_location:
- ntifs.h
api_name:
- ECP_OPEN_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: ECP_OPEN_PARAMETERS, *PECP_OPEN_PARAMETERS
---

# ECP_OPEN_PARAMETERS structure

## -description

The ECP_OPEN_PARAMETERS structure allows a caller to specify the purpose of opening of a file without interfering with existing handles and/or opportunistic locks (oplocks) on the file.

## -struct-fields

### -field Size

Specifies the size of this context structure, in bytes.

### -field Reserved

Reserved for future use. This must be initialized to 0.

### -field Flags

Flags that specify the parameters or purpose for opening a file. *Flags* can be any combination of the following values:

| Value | Description |
| ----- | ----------- |
| ECP_OPEN_PARAMETERS_FLAG_OPEN_FOR_READ (0x0001) | Opening file to read it. |
| ECP_OPEN_PARAMETERS_FLAG_OPEN_FOR_WRITE (0x0002) | Opening file to write to it. |
| ECP_OPEN_PARAMETERS_FLAG_OPEN_FOR_DELETE (0x0004) | Opening file to delete it. |
| ECP_OPEN_PARAMETERS_FLAG_IGNORE_DIR_CASE_SENSITIVITY (0x0008) | Forces a case-insensitive lookup for this file open, even under a case-sensitive directory. The next version of Windows 10. |
| ECP_OPEN_PARAMETERS_FLAG_FAIL_ON_CASE_SENSITIVE_DIR ( 0x0010) | Fails the file open or create request if the path has any case sensitive directories. The next version of Windows 10. |

## -remarks

The ECP_OPEN_PARAMETERS_FLAG_OPEN_FOR_READ and ECP_OPEN_PARAMETERS_FLAG_OPEN_FOR_WRITE flags allow read/write access to encrypted files without having to actually open such files for read/write access. These ECP flags allow a kernel-mode component to open for metadata-only access, thus not interfering with other access while still getting the encryption context setup in order to do read/writes. A filter can set these flags to avoid conflicts with locking. Setting up the encryption state for read/write operations is expensive and are not typically done when files aren't opened for read/write access.

## -see-also

[**FltAllocateExtraCreateParameterList**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocateextracreateparameterlist)

[**FltCreateFileEx2**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcreatefileex2)
