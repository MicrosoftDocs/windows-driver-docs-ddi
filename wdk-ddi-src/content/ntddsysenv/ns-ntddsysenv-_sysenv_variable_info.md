---
UID: NS:ntddsysenv._SYSENV_VARIABLE_INFO
title: "_SYSENV_VARIABLE_INFO"
author: windows-driver-content
description: Stores the information about a system environment variable using SysEnv device. This structure is used in the IOCTL_SYSENV_QUERY_VARIABLE_INFO request.
old-location: kernel\sysenv_variable_info.htm
old-project: kernel
ms.assetid: D9C7BB96-1E26-4D89-9CBE-074232FD0752
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PSYSENV_VARIABLE_INFO, PSYSENV_VARIABLE_INFO, PSYSENV_VARIABLE_INFO structure pointer [Kernel-Mode Driver Architecture], SYSENV_VARIABLE_INFO, SYSENV_VARIABLE_INFO structure [Kernel-Mode Driver Architecture], _SYSENV_VARIABLE_INFO, kernel.sysenv_variable_info, ntddsysenv/PSYSENV_VARIABLE_INFO, ntddsysenv/SYSENV_VARIABLE_INFO"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddsysenv.h
api_name:
-	SYSENV_VARIABLE_INFO
product: Windows
targetos: Windows
req.typenames: SYSENV_VARIABLE_INFO, *PSYSENV_VARIABLE_INFO
---

# _SYSENV_VARIABLE_INFO structure


## -description


Stores the information about a system environment variable using
    SysEnv device. This structure is used in the <a href="..\ntddsysenv\ni-ntddsysenv-ioctl_sysenv_query_variable_info.md">IOCTL_SYSENV_QUERY_VARIABLE_INFO</a> request.


## -syntax


````
typedef struct _SYSENV_VARIABLE_INFO {
  ULONGLONG MaximumVariableStorageSize;
  ULONGLONG RemainingVariableStorageSize;
  ULONGLONG MaximumVariableSize;
} SYSENV_VARIABLE_INFO, *PSYSENV_VARIABLE_INFO;
````


## -struct-fields




### -field MaximumVariableStorageSize

The size of the variable.


### -field RemainingVariableStorageSize

The remaining size of the variable.


### -field MaximumVariableSize

The maximum size of the variable.


## -see-also

<a href="..\ntddsysenv\ni-ntddsysenv-ioctl_sysenv_query_variable_info.md">IOCTL_SYSENV_QUERY_VARIABLE_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20SYSENV_VARIABLE_INFO structure%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

