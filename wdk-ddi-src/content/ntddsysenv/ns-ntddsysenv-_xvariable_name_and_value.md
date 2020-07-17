---
UID: NS:ntddsysenv._XVARIABLE_NAME_AND_VALUE
title: _XVARIABLE_NAME_AND_VALUE (ntddsysenv.h)
description: Stores the name and value of a system environment variable using SysEnv device. This structure is used in the IOCTL_SYSENV_ENUM_VARIABLES and IOCTL_SYSENV_SET_VARIABLE requests.
old-location: kernel\xvariable_name_and_value.htm
tech.root: kernel
ms.assetid: 46E892A7-2813-4C50-BE91-B5267696E2A5
ms.date: 04/30/2018
keywords: ["_XVARIABLE_NAME_AND_VALUE structure"]
ms.keywords: "*PSYSENV_VARIABLE_AND_VALUE, *PXVARIABLE_NAME_AND_VALUE, PXVARIABLE_NAME_AND_VALUE, PXVARIABLE_NAME_AND_VALUE structure pointer [Kernel-Mode Driver Architecture], SYSENV_VARIABLE_AND_VALUE, XVARIABLE_NAME_AND_VALUE, XVARIABLE_NAME_AND_VALUE structure [Kernel-Mode Driver Architecture], _XVARIABLE_NAME_AND_VALUE, kernel.xvariable_name_and_value, ntddsysenv/PXVARIABLE_NAME_AND_VALUE, ntddsysenv/XVARIABLE_NAME_AND_VALUE"
f1_keywords:
 - "ntddsysenv/XVARIABLE_NAME_AND_VALUE"
 - "XVARIABLE_NAME_AND_VALUE"
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
- XVARIABLE_NAME_AND_VALUE
product:
- Windows
targetos: Windows
req.typenames: XVARIABLE_NAME_AND_VALUE, *PXVARIABLE_NAME_AND_VALUE
---

# _XVARIABLE_NAME_AND_VALUE structure


## -description


Stores the name and value of a system environment variable using
    SysEnv device. This structure is used in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddsysenv/ni-ntddsysenv-ioctl_sysenv_enum_variables">IOCTL_SYSENV_ENUM_VARIABLES</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddsysenv/ni-ntddsysenv-ioctl_sysenv_set_variable">IOCTL_SYSENV_SET_VARIABLE</a> requests.


## -struct-fields




### -field NextEntryOffset

The location of the next entry in the array of XVARIABLE_NAME structures reprieved by the  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddsysenv/ni-ntddsysenv-ioctl_sysenv_enum_variables">IOCTL_SYSENV_ENUM_VARIABLES</a> request.


### -field ValueOffset

The value of the system environment variable.


### -field ValueLength

The length of the value.


### -field Attributes

Attributes of the system environment variable.


### -field VendorGuid

The vendor GUID.


### -field Name

Name of the system environment variable.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddsysenv/ni-ntddsysenv-ioctl_sysenv_enum_variables">IOCTL_SYSENV_ENUM_VARIABLES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddsysenv/ni-ntddsysenv-ioctl_sysenv_set_variable">IOCTL_SYSENV_SET_VARIABLE</a>
 

 

