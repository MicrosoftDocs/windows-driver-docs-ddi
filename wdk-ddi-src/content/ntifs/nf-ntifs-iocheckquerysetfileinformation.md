---
UID: NF:ntifs.IoCheckQuerySetFileInformation
title: IoCheckQuerySetFileInformation function (ntifs.h)
description: "Microsoft reserves the IoCheckQuerySetFileInformation function for internal use only. Don't use this function in your code."
old-location: ifsk\iocheckquerysetfileinformation.htm
tech.root: ifsk
ms.date: 05/30/2019
keywords: ["IoCheckQuerySetFileInformation function"]
ms.keywords: IoCheckQuerySetFileInformation, IoCheckQuerySetFileInformation function [Installable File System Drivers], ifsk.iocheckquerysetfileinformation, ioref_22478455-1bd1-46cb-8ac2-05e4857c9524.xml, ntifs/IoCheckQuerySetFileInformation
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
 - IoCheckQuerySetFileInformation
 - ntifs/IoCheckQuerySetFileInformation
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - IoCheckQuerySetFileInformation
---

# IoCheckQuerySetFileInformation function


## -description

The **IoCheckQuerySetFileInformation** routine checks the validity of the parameters for either a query or set file information operation.

## -parameters

### -param FileInformationClass

A [FILE_INFORMATION_CLASS](../wdm/ne-wdm-_file_information_class.md) enum value that specifies the file information class to be checked.

### -param Length

Size, in bytes, of the buffer required for the specified file information operation.

### -param SetOperation

Boolean value that specifies the operation type. If *SetOperation* is **TRUE**, the operation is a set file operation; if **FALSE,** it is a query file operation.

## -returns

**IoCheckQuerySetFileInformation** returns STATUS_SUCCESS if the parameters are valid; otherwise, it returns one of the following error codes.

| Return Code | Description |
| ----------- | ----------- |
| STATUS_INVALID_INFO_CLASS | The value specified in *FileInformationClass* is not a valid information class. |
| STATUS_INFO_LENGTH_MISMATCH | The buffer size specified in *Length* is smaller than the buffer size required for the specified file operation. |

## -remarks

 **IoCheckQuerySetFileInformation** is used primarily by network servers running in kernel mode since no such parameter validity checking is done in the normal path.

## -see-also

[FILE_INFORMATION_CLASS](../wdm/ne-wdm-_file_information_class.md)

[ZwQueryInformationFile](nf-ntifs-ntqueryinformationfile.md)

[ZwSetInformationFile](nf-ntifs-ntsetinformationfile.md)
