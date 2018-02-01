---
UID: NS:wdm._KEY_WRITE_TIME_INFORMATION
title: "_KEY_WRITE_TIME_INFORMATION"
author: windows-driver-content
description: The KEY_WRITE_TIME_INFORMATION structure is used by the system to set the last write time for a registry key.
old-location: kernel\key_write_time_information.htm
old-project: kernel
ms.assetid: 44f68a5a-c7ad-4555-b6b2-6461ac17960a
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdm/KEY_WRITE_TIME_INFORMATION, kstruct_c_373f0047-919b-44c4-8831-181027ba5f2e.xml, KEY_WRITE_TIME_INFORMATION structure [Kernel-Mode Driver Architecture], PKEY_WRITE_TIME_INFORMATION, *PKEY_WRITE_TIME_INFORMATION, KEY_WRITE_TIME_INFORMATION, PKEY_WRITE_TIME_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _KEY_WRITE_TIME_INFORMATION, kernel.key_write_time_information, wdm/PKEY_WRITE_TIME_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available on Microsoft Windows XP and later versions of the Windows operating system.
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdm.h
apiname:
-	KEY_WRITE_TIME_INFORMATION
product: Windows
targetos: Windows
req.typenames: "*PKEY_WRITE_TIME_INFORMATION, KEY_WRITE_TIME_INFORMATION"
req.product: Windows 10 or later.
---

# _KEY_WRITE_TIME_INFORMATION structure


## -description


The <b>KEY_WRITE_TIME_INFORMATION</b> structure is used by the system to set the last write time for a registry key.


## -syntax


````
typedef struct _KEY_WRITE_TIME_INFORMATION {
  LARGE_INTEGER LastWriteTime;
} KEY_WRITE_TIME_INFORMATION, *PKEY_WRITE_TIME_INFORMATION;
````


## -struct-fields




### -field LastWriteTime

Specifies the last time that the key was changed. This time value is expressed in absolute system time format. Absolute system time is the number of 100-nanosecond intervals since the start of the year 1601 in the Gregorian calendar. 


## -see-also

<a href="..\wdm\ne-wdm-_key_set_information_class.md">KEY_SET_INFORMATION_CLASS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KEY_WRITE_TIME_INFORMATION structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

