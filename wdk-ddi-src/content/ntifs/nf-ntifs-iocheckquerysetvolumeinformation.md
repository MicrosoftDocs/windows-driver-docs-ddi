---
UID: NF:ntifs.IoCheckQuerySetVolumeInformation
title: IoCheckQuerySetVolumeInformation function (ntifs.h)
description: "Microsoft reserves the IoCheckQuerySetVolumeInformation function for internal use only. Don't use this function in your code."
old-location: ifsk\iocheckquerysetvolumeinformation.htm
tech.root: ifsk
ms.date: 05/30/2019
keywords: ["IoCheckQuerySetVolumeInformation function"]
ms.keywords: IoCheckQuerySetVolumeInformation, IoCheckQuerySetVolumeInformation function [Installable File System Drivers], ifsk.iocheckquerysetvolumeinformation, ioref_67d57dbb-a3b0-4f78-9454-36c8b04e515c.xml, ntifs/IoCheckQuerySetVolumeInformation
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
 - IoCheckQuerySetVolumeInformation
 - ntifs/IoCheckQuerySetVolumeInformation
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - IoCheckQuerySetVolumeInformation
---

# IoCheckQuerySetVolumeInformation function


## -description

The **IoCheckQuerySetVolumeInformation** routine checks the validity of the parameters for either a query or set volume information operation.

## -parameters

### -param FsInformationClass

A [FS_INFORMATION_CLASS](../wdm/ne-wdm-_fsinfoclass.md) enum value that specifies the information class to be checked.

### -param Length

Size, in bytes, of the buffer required for the specified information operation.

### -param SetOperation

Boolean value that specifies the operation type. If *SetOperation* is **TRUE**, the operation is a set volume operation; if **FALSE,** it is a query volume operation.

## -returns

**IoCheckQuerySetVolumeInformation** returns STATUS_SUCCESS if the parameters are valid; otherwise, it returns one of the following error codes.

| Return Code | Description |
| ----------- | ----------- |
| STATUS_INVALID_INFO_CLASS | The value specified in *FsInformationClass* is not a valid information class. |
| STATUS_INFO_LENGTH_MISMATCH | The buffer size specified in *Length* is smaller than the buffer size required for the specified volume operation. |

## -remarks

 **IoCheckQuerySetVolumeInformation** is used primarily by network servers running in kernel mode since no such parameter validity checking is done in the normal path.

## -see-also

[FS_INFORMATION_CLASS](../wdm/ne-wdm-_fsinfoclass.md)

[ZwQueryVolumeInformationFile](../ntddk/nf-ntddk-zwqueryvolumeinformationfile.md)

[ZwSetVolumeInformationFile](./nf-ntifs-zwsetvolumeinformationfile.md)
