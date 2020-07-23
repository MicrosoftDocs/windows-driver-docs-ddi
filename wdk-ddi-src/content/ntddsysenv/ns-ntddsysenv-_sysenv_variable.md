---
UID: NS:ntddsysenv._SYSENV_VARIABLE
title: _SYSENV_VARIABLE (ntddsysenv.h)
description: Stores the name a system environment variable using SysEnv device. This structure is used in the IOCTL_SYSENV_GET_VARIABLE request.
old-location: kernel\sysenv_variable.htm
tech.root: kernel
ms.assetid: 311A5977-C3F5-4287-B030-00F4BB9C8629
ms.date: 04/30/2018
keywords: ["_SYSENV_VARIABLE structure"]
ms.keywords: "*PSYSENV_VARIABLE, PSYSENV_VARIABLE, PSYSENV_VARIABLE structure pointer [Kernel-Mode Driver Architecture], SYSENV_VARIABLE, SYSENV_VARIABLE structure [Kernel-Mode Driver Architecture], _SYSENV_VARIABLE, kernel.sysenv_variable, ntddsysenv/PSYSENV_VARIABLE, ntddsysenv/SYSENV_VARIABLE"
f1_keywords:
 - "ntddsysenv/SYSENV_VARIABLE"
 - "SYSENV_VARIABLE"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddsysenv.h
api_name:
- SYSENV_VARIABLE
targetos: Windows
req.typenames: SYSENV_VARIABLE, *PSYSENV_VARIABLE
---

# _SYSENV_VARIABLE structure


## -description


Stores the name a system environment variable using
    SysEnv device. This structure is used in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddsysenv/ni-ntddsysenv-ioctl_sysenv_get_variable">IOCTL_SYSENV_GET_VARIABLE</a> request.


## -struct-fields




### -field VendorGuid

The vendor GUID.


### -field VariableNameLength

The length of the string pointed to by  <b>VariableName</b>, which contains the name of the variable.


### -field VariableName

A string that  contains the name of the variable.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddsysenv/ni-ntddsysenv-ioctl_sysenv_get_variable">IOCTL_SYSENV_GET_VARIABLE</a>
 

 

