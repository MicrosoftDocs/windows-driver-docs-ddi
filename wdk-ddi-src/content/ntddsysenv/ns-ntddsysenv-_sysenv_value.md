---
UID: NS:ntddsysenv._SYSENV_VALUE
title: _SYSENV_VALUE (ntddsysenv.h)
description: Stores the value of a system environment variable using SysEnv device. This structure is used in the IOCTL_SYSENV_GET_VARIABLE request.
old-location: kernel\sysenv_value.htm
tech.root: kernel
ms.assetid: 4F79D820-29D4-4D38-A09C-8A5E968C1479
ms.date: 04/30/2018
ms.keywords: "*PSYSENV_VALUE, PSYSENV_VALUE, PSYSENV_VALUE structure pointer [Kernel-Mode Driver Architecture], SYSENV_VALUE, SYSENV_VALUE structure [Kernel-Mode Driver Architecture], _SYSENV_VALUE, kernel.sysenv_value, ntddsysenv/PSYSENV_VALUE, ntddsysenv/SYSENV_VALUE"
ms.topic: struct
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
- SYSENV_VALUE
product:
- Windows
targetos: Windows
req.typenames: SYSENV_VALUE, *PSYSENV_VALUE
---

# _SYSENV_VALUE structure


## -description


Stores the value of a system environment variable using
    SysEnv device. This structure is used in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddsysenv/ni-ntddsysenv-ioctl_sysenv_get_variable">IOCTL_SYSENV_GET_VARIABLE</a> request.


## -struct-fields




### -field Attributes

Attributes of the system environment variable.


### -field ValueLength

The length of the value of the system environment variable.


### -field ValueData

 




#### - UCHAR

The value of the system environment variable.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddsysenv/ni-ntddsysenv-ioctl_sysenv_get_variable">IOCTL_SYSENV_GET_VARIABLE</a>
 

 

