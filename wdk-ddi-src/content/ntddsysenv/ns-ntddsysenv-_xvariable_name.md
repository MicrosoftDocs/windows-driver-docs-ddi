---
UID: NS:ntddsysenv._XVARIABLE_NAME
title: "_XVARIABLE_NAME"
author: windows-driver-content
description: Stores the name of a system environment variable using SysEnv device. This structure is used in the IOCTL_SYSENV_ENUM_VARIABLES request.
old-location: kernel\xvariable_name.htm
old-project: kernel
ms.assetid: DF02AB1E-6803-492C-9261-400177497195
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: "*PSYSENV_VARIABLE_NAME, PXVARIABLE_NAME, _XVARIABLE_NAME, SYSENV_VARIABLE_NAME, kernel.xvariable_name, ntddsysenv/PXVARIABLE_NAME, *PXVARIABLE_NAME, XVARIABLE_NAME, XVARIABLE_NAME structure [Kernel-Mode Driver Architecture], ntddsysenv/XVARIABLE_NAME, PXVARIABLE_NAME structure pointer [Kernel-Mode Driver Architecture]"
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
-	XVARIABLE_NAME
product: Windows
targetos: Windows
req.typenames: "*PXVARIABLE_NAME, XVARIABLE_NAME"
---

# _XVARIABLE_NAME structure


## -description


Stores the name of a system environment variable using
    SysEnv device. This structure is used in the <a href="..\ntddsysenv\ni-ntddsysenv-ioctl_sysenv_enum_variables.md">IOCTL_SYSENV_ENUM_VARIABLES</a> request.


## -syntax


````
typedef struct _XVARIABLE_NAME {
  ULONG NextEntryOffset;
  GUID  VendorGuid;
  WCHAR Name[ANYSIZE_ARRAY];
} XVARIABLE_NAME, *PXVARIABLE_NAME;
````


## -struct-fields




### -field NextEntryOffset

The location of the next entry in the array of <b>XVARIABLE_NAME</b> structures reprieved by the  <a href="..\ntddsysenv\ni-ntddsysenv-ioctl_sysenv_enum_variables.md">IOCTL_SYSENV_ENUM_VARIABLES</a> request.


### -field VendorGuid

The vendor GUID.


### -field Name

Name of the system environment variable.


## -see-also

<a href="..\ntddsysenv\ni-ntddsysenv-ioctl_sysenv_enum_variables.md">IOCTL_SYSENV_ENUM_VARIABLES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20XVARIABLE_NAME structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

