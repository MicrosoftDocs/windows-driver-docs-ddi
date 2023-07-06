---
UID: NS:ntifs._WIM_PROVIDER_EXTERNAL_INFO
title: WIM_PROVIDER_EXTERNAL_INFO (ntifs.h)
description: Learn more about the WIM_PROVIDER_EXTERNAL_INFO structure.
tech.root: ifsk
ms.date: 07/06/2023
keywords: ["WIM_PROVIDER_EXTERNAL_INFO structure"]
ms.keywords: "*PWIM_PROVIDER_EXTERNAL_INFO, PWIM_PROVIDER_EXTERNAL_INFO, PWIM_PROVIDER_EXTERNAL_INFO structure pointer [Installable File System Drivers], WIM_PROVIDER_EXTERNAL_FLAG_NOT_ACTIVE, WIM_PROVIDER_EXTERNAL_FLAG_SUSPENDED, WIM_PROVIDER_EXTERNAL_INFO, WIM_PROVIDER_EXTERNAL_INFO structure [Installable File System Drivers], _WIM_PROVIDER_EXTERNAL_INFO, ifsk.wim_provider_external_info, ntifs/PWIM_PROVIDER_EXTERNAL_INFO, ntifs/WIM_PROVIDER_EXTERNAL_INFO"
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1 Update
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
req.typenames: WIM_PROVIDER_EXTERNAL_INFO, *PWIM_PROVIDER_EXTERNAL_INFO
f1_keywords:
 - _WIM_PROVIDER_EXTERNAL_INFO
 - ntifs/_WIM_PROVIDER_EXTERNAL_INFO
 - PWIM_PROVIDER_EXTERNAL_INFO
 - ntifs/PWIM_PROVIDER_EXTERNAL_INFO
 - WIM_PROVIDER_EXTERNAL_INFO
 - ntifs/WIM_PROVIDER_EXTERNAL_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _WIM_PROVIDER_EXTERNAL_INFO
 - PWIM_PROVIDER_EXTERNAL_INFO
 - WIM_PROVIDER_EXTERNAL_INFO
---

# WIM_PROVIDER_EXTERNAL_INFO structure

## -description

The **WIM_PROVIDER_EXTERNAL_INFO** structure holds the identifier and status information for the Windows Image File (WIM) external backing provider.

## -struct-fields

### -field Version

The WIM provider version. Set to WIM_PROVIDER_CURRENT_VERSION.

### -field Flags

The status flags for the WIM provider. Set to 0 when active. Otherwise **Flags** is set to one of the following values.

| Value | Meaning |
| ----- | ------- |
| WIM_PROVIDER_EXTERNAL_FLAG_NOT_ACTIVE | The WIM provider is not active, which can occur when the WIM file is not found. In this case, the WIM file will not be recovered. |
| WIM_PROVIDER_EXTERNAL_FLAG_SUSPENDED  | Indicates that the provider is dismounted. Recovery will be attempted. |

### -field DataSourceId

An identifier value for the WIM file data source.

### -field ResourceHash

An identifier for the object contained within the WIM.  Conventionally a hash of the contents of a file, stored within the WIM.

## -remarks

The backing source for a file is set with a [**FSCTL_SET_EXTERNAL_BACKING**](/windows-hardware/drivers/ifs/fsctl-set-external-backing) control code request. The WIM file backing the file specified in the request is set in the **DataSourceId** member of **WIM_PROVIDER_EXTERNAL_INFO**.

The **Flags** and **ResourceHash** members are valid when the provider info is returned from a [**FSCTL_GET_EXTERNAL_BACKING**](/windows-hardware/drivers/ifs/fsctl-get-external-backing) request.

## -see-also

[**FSCTL_GET_EXTERNAL_BACKING**](/windows-hardware/drivers/ifs/fsctl-get-external-backing)

[**FSCTL_SET_EXTERNAL_BACKING**](/windows-hardware/drivers/ifs/fsctl-set-external-backing)
