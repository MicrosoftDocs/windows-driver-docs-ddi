---
UID: NS:ntddsysenv._XVARIABLE_NAME_AND_VALUE
title: "_XVARIABLE_NAME_AND_VALUE"
author: windows-driver-content
description: Stores the name and value of a system environment variable using SysEnv device. This structure is used in the IOCTL_SYSENV_ENUM_VARIABLES and IOCTL_SYSENV_SET_VARIABLE requests.
old-location: kernel\xvariable_name_and_value.htm
old-project: kernel
ms.assetid: 46E892A7-2813-4C50-BE91-B5267696E2A5
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PSYSENV_VARIABLE_AND_VALUE, *PXVARIABLE_NAME_AND_VALUE, ,, A, B, D, E, I, L, M, N, P, PXVARIABLE_NAME_AND_VALUE, PXVARIABLE_NAME_AND_VALUE structure pointer [Kernel-Mode Driver Architecture], R, S, SYSENV_VARIABLE_AND_VALUE, U, V, X, XVARIABLE_NAME_AND_VALUE, XVARIABLE_NAME_AND_VALUE structure [Kernel-Mode Driver Architecture], Y, _, _XVARIABLE_NAME_AND_VALUE, kernel.xvariable_name_and_value, ntddsysenv/PXVARIABLE_NAME_AND_VALUE, ntddsysenv/XVARIABLE_NAME_AND_VALUE"
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddsysenv.h
apiname:
-	XVARIABLE_NAME_AND_VALUE
product: Windows
targetos: Windows
req.typenames: XVARIABLE_NAME_AND_VALUE, *PXVARIABLE_NAME_AND_VALUE
---

# _XVARIABLE_NAME_AND_VALUE structure


## -description


Stores the name and value of a system environment variable using
    SysEnv device. This structure is used in the <a href="..\ntddsysenv\ni-ntddsysenv-ioctl_sysenv_enum_variables.md">IOCTL_SYSENV_ENUM_VARIABLES</a> and <a href="..\ntddsysenv\ni-ntddsysenv-ioctl_sysenv_set_variable.md">IOCTL_SYSENV_SET_VARIABLE</a> requests.


## -syntax


````
typedef struct _XVARIABLE_NAME_AND_VALUE {
  ULONG 				NextEntryOffset;
  ULONG ValueOffset;
  ULONG ValueLength;
  ULONG Attributes;
  GUID  VendorGuid;
  WCHAR Name[ANYSIZE_ARRAY];
} XVARIABLE_NAME_AND_VALUE, *PXVARIABLE_NAME_AND_VALUE;
````


## -struct-fields




### -field NextEntryOffset

The location of the next entry in the array of XVARIABLE_NAME structures reprieved by the  <a href="..\ntddsysenv\ni-ntddsysenv-ioctl_sysenv_enum_variables.md">IOCTL_SYSENV_ENUM_VARIABLES</a> request.


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

<a href="..\ntddsysenv\ni-ntddsysenv-ioctl_sysenv_set_variable.md">IOCTL_SYSENV_SET_VARIABLE</a>



<a href="..\ntddsysenv\ni-ntddsysenv-ioctl_sysenv_enum_variables.md">IOCTL_SYSENV_ENUM_VARIABLES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20XVARIABLE_NAME_AND_VALUE structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

