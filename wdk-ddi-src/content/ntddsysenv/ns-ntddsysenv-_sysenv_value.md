---
UID: NS:ntddsysenv._SYSENV_VALUE
title: "_SYSENV_VALUE"
author: windows-driver-content
description: Stores the value of a system environment variable using SysEnv device. This structure is used in the IOCTL_SYSENV_GET_VARIABLE request.
old-location: kernel\sysenv_value.htm
old-project: kernel
ms.assetid: 4F79D820-29D4-4D38-A09C-8A5E968C1479
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ntddsysenv/SYSENV_VALUE, *PSYSENV_VALUE, SYSENV_VALUE, ntddsysenv/PSYSENV_VALUE, PSYSENV_VALUE structure pointer [Kernel-Mode Driver Architecture], _SYSENV_VALUE, kernel.sysenv_value, SYSENV_VALUE structure [Kernel-Mode Driver Architecture], PSYSENV_VALUE
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
-	SYSENV_VALUE
product: Windows
targetos: Windows
req.typenames: SYSENV_VALUE, *PSYSENV_VALUE
---

# _SYSENV_VALUE structure


## -description


Stores the value of a system environment variable using
    SysEnv device. This structure is used in the <a href="https://msdn.microsoft.com/library/windows/hardware/mt791526">IOCTL_SYSENV_GET_VARIABLE</a> request.


## -syntax


````
typedef struct _SYSENV_VALUE {
  ULONG     Attributes;
  ULONG     ValueLength;
  ValueData UCHAR[ANYSIZE_ARRAY];
} SYSENV_VALUE, *PSYSENV_VALUE;
````


## -struct-fields




#### - Attributes

Attributes of the system environment variable.


#### - ValueLength

The length of the value of the system environment variable.


### -field ValueData

 



#### - UCHAR

The value of the system environment variable.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt791526">IOCTL_SYSENV_GET_VARIABLE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20SYSENV_VALUE structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

