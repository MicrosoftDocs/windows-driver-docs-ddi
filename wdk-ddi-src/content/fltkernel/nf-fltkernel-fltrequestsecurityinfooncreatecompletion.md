---
UID: NF:fltkernel.FltRequestSecurityInfoOnCreateCompletion
title: FltRequestSecurityInfoOnCreateCompletion function
description: A minifilter calls FltRequestSecurityInfoOnCreateCompletion during file pre-create to request that the file system stores the file security information for retrieval upon create complete.
tech.root: ifsk
ms.date: 01/11/2019
keywords: ["FltRequestSecurityInfoOnCreateCompletion function"]
ms.keywords: FltRequestSecurityInfoOnCreateCompletion, FltRetrieveFileInfoOnCreateCompletion, FltRetrieveFileInfoOnCreateCompletionEx
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: 
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
f1_keywords:
 - FltRequestSecurityInfoOnCreateCompletion
 - fltkernel/FltRequestSecurityInfoOnCreateCompletion
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - fltkernel.h
api_name:
 - FltRequestSecurityInfoOnCreateCompletion
---

# FltRequestSecurityInfoOnCreateCompletion function


## -description

A minifilter calls **FltRequestSecurityInfoOnCreateCompletion** during file pre-create to request that the file system stores file security information for retrieval during post create.

## -parameters

### -param Filter

Opaque filter pointer that uniquely identifies the minifilter driver.

### -param Data

Pointer to the [**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md) callback data representing the I/O create operation.

### -param SecurityInformation

[**SECURITY_INFORMATION**](/windows-hardware/drivers/ifs/security-information) value specifying the information to be set as a combination of one or more of the following. 

| Value | Meaning |
| ----- | ------- |
| OWNER_SECURITY_INFORMATION | Indicates the owner identifier of the object is to be set. Requires WRITE_OWNER access. |
| GROUP_SECURITY_INFORMATION | Indicates the primary group identifier of the object is to be set. Requires WRITE_OWNER access. |
| DACL_SECURITY_INFORMATION | Indicates the discretionary access control list (DACL) of the object is to be set. Requires WRITE_DAC access. |
| SACL_SECURITY_INFORMATION | Indicates the system ACL (SACL) of the object is to be set. Requires ACCESS_SYSTEM_SECURITY access. |

## -returns

**FltRequestSecurityInfoOnCreateCompletion** can return one of the following values:

| Return code | Description |
| ----------- | ----------- |
| **STATUS_SUCCESS** | The file system successfully stored the requested file security information. |
| **STATUS_INSUFFICIENT_RESOURCES** | **FltRequestSecurityInfoOnCreateCompletion** was unable to allocate sufficient memory in which to store the requested file information. |
| **STATUS_INVALID_PARAMETER_2** | The provided callback data object was not an IRP-based create operation. |

## -remarks

The minifilter can retrieve the file information by calling [**FltRetrieveFileInfoOnCreateCompletionEx**](nf-fltkernel-fltretrievefileinfooncreatecompletionex.md) or [**FltRetrieveFileInfoOnCreateCompletion**](nf-fltkernel-fltretrievefileinfooncreatecompletion.md) during post create. A minifilter's performance is typically better when it requests and retrieves file information in this manner, rather than querying file information at a later time.

## -see-also

[**FltRetrieveFileInfoOnCreateCompletion**](nf-fltkernel-fltretrievefileinfooncreatecompletion.md)

[**FltRetrieveFileInfoOnCreateCompletionEx**](nf-fltkernel-fltretrievefileinfooncreatecompletionex.md)

