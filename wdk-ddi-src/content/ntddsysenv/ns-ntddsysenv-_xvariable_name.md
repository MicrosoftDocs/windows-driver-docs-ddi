---
UID: NS:ntddsysenv._XVARIABLE_NAME
title: _XVARIABLE_NAME (ntddsysenv.h)
description: Stores the name of a system environment variable using SysEnv device. This structure is used in the IOCTL_SYSENV_ENUM_VARIABLES request.
old-location: kernel\xvariable_name.htm
tech.root: kernel
ms.assetid: DF02AB1E-6803-492C-9261-400177497195
ms.date: 04/30/2018
keywords: ["XVARIABLE_NAME structure"]
ms.keywords: "*PSYSENV_VARIABLE_NAME, *PXVARIABLE_NAME, PXVARIABLE_NAME, PXVARIABLE_NAME structure pointer [Kernel-Mode Driver Architecture], SYSENV_VARIABLE_NAME, XVARIABLE_NAME, XVARIABLE_NAME structure [Kernel-Mode Driver Architecture], _XVARIABLE_NAME, kernel.xvariable_name, ntddsysenv/PXVARIABLE_NAME, ntddsysenv/XVARIABLE_NAME"
req.header: ntddsysenv.h
req.include-header: 
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
req.typenames: XVARIABLE_NAME, *PXVARIABLE_NAME
f1_keywords:
 - _XVARIABLE_NAME
 - ntddsysenv/_XVARIABLE_NAME
 - PXVARIABLE_NAME
 - ntddsysenv/PXVARIABLE_NAME
 - XVARIABLE_NAME
 - ntddsysenv/XVARIABLE_NAME
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddsysenv.h
api_name:
 - XVARIABLE_NAME
---

# _XVARIABLE_NAME structure


## -description

Stores the name of a system environment variable using
    SysEnv device. This structure is used in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddsysenv/ni-ntddsysenv-ioctl_sysenv_enum_variables">IOCTL_SYSENV_ENUM_VARIABLES</a> request.

## -struct-fields

### -field NextEntryOffset

The location of the next entry in the array of <b>XVARIABLE_NAME</b> structures reprieved by the  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddsysenv/ni-ntddsysenv-ioctl_sysenv_enum_variables">IOCTL_SYSENV_ENUM_VARIABLES</a> request.

### -field VendorGuid

The vendor GUID.

### -field Name

Name of the system environment variable.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddsysenv/ni-ntddsysenv-ioctl_sysenv_enum_variables">IOCTL_SYSENV_ENUM_VARIABLES</a>

