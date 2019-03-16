---
UID: NS:wdm._KEY_BASIC_INFORMATION
title: _KEY_BASIC_INFORMATION (wdm.h)
description: The KEY_BASIC_INFORMATION structure defines a subset of the full information that is available for a registry key.
old-location: kernel\key_basic_information.htm
tech.root: kernel
ms.assetid: 789c60b6-a5a4-4570-bb0c-acfe1166a302
ms.date: 04/30/2018
ms.keywords: "*PKEY_BASIC_INFORMATION, KEY_BASIC_INFORMATION, KEY_BASIC_INFORMATION structure [Kernel-Mode Driver Architecture], PKEY_BASIC_INFORMATION, PKEY_BASIC_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _KEY_BASIC_INFORMATION, kernel.key_basic_information, kstruct_c_85ec4926-6fc1-42c1-8992-dd37ee92e5cf.xml, wdm/KEY_BASIC_INFORMATION, wdm/PKEY_BASIC_INFORMATION"
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
- Wdm.h
api_name:
- KEY_BASIC_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: KEY_BASIC_INFORMATION, *PKEY_BASIC_INFORMATION
---

# _KEY_BASIC_INFORMATION structure


## -description


The <b>KEY_BASIC_INFORMATION</b> structure defines a subset of the full information that is available for a registry key.


## -struct-fields




### -field LastWriteTime

The last time this key or any of its values changed. This time value is expressed in absolute system time format. Absolute system time is the number of 100-nanosecond intervals since the start of the year 1601 in the Gregorian calendar.


### -field TitleIndex

Device and intermediate drivers should ignore this member.


### -field NameLength

The size, in bytes, of the key name string in the <b>Name</b> array.


### -field Name

An array of wide characters that contains the name of the registry key. This character string is <u>not</u> null-terminated. Only the first element in this array is included in the <b>KEY_BASIC_INFORMATION</b> structure definition. The storage for the remaining elements in the array immediately follows this element.


## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/ff566447">ZwEnumerateKey</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff567060">ZwQueryKey</a> routines use the <b>KEY_BASIC_INFORMATION</b> structure to contain the basic information for a registry key. When the <i>KeyInformationClass</i> parameter of either routine is <b>KeyBasicInformation</b>, the <i>KeyInformation</i> buffer is treated as a <b>KEY_BASIC_INFORMATION</b> structure.  For more information about the <b>KeyBasicInformation</b> enumeration value, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff553373">KEY_INFORMATION_CLASS</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553358">KEY_CACHED_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553367">KEY_FULL_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553373">KEY_INFORMATION_CLASS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553381">KEY_NAME_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553392">KEY_NODE_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554221">KEY_VIRTUALIZATION_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566447">ZwEnumerateKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567060">ZwQueryKey</a>
 

 

