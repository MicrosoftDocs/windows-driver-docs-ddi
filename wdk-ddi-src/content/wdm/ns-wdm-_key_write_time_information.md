---
UID: NS:wdm._KEY_WRITE_TIME_INFORMATION
title: "_KEY_WRITE_TIME_INFORMATION"
author: windows-driver-content
description: The KEY_WRITE_TIME_INFORMATION structure is used by the system to set the last write time for a registry key.
old-location: kernel\key_write_time_information.htm
tech.root: kernel
ms.assetid: 44f68a5a-c7ad-4555-b6b2-6461ac17960a
ms.date: 04/30/2018
ms.keywords: "*PKEY_WRITE_TIME_INFORMATION, KEY_WRITE_TIME_INFORMATION, KEY_WRITE_TIME_INFORMATION structure [Kernel-Mode Driver Architecture], PKEY_WRITE_TIME_INFORMATION, PKEY_WRITE_TIME_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _KEY_WRITE_TIME_INFORMATION, kernel.key_write_time_information, kstruct_c_373f0047-919b-44c4-8831-181027ba5f2e.xml, wdm/KEY_WRITE_TIME_INFORMATION, wdm/PKEY_WRITE_TIME_INFORMATION"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	KEY_WRITE_TIME_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: KEY_WRITE_TIME_INFORMATION, *PKEY_WRITE_TIME_INFORMATION
---

# _KEY_WRITE_TIME_INFORMATION structure


## -description


The <b>KEY_WRITE_TIME_INFORMATION</b> structure is used by the system to set the last write time for a registry key.


## -struct-fields




### -field LastWriteTime

Specifies the last time that the key was changed. This time value is expressed in absolute system time format. Absolute system time is the number of 100-nanosecond intervals since the start of the year 1601 in the Gregorian calendar. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553399">KEY_SET_INFORMATION_CLASS</a>
 

 

