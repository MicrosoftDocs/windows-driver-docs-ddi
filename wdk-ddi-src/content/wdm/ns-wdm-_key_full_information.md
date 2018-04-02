---
UID: NS:wdm._KEY_FULL_INFORMATION
title: "_KEY_FULL_INFORMATION"
author: windows-driver-content
description: The KEY_FULL_INFORMATION structure defines the information available for a registry key, including information about its subkeys and the maximum length for their names and value entries.
old-location: kernel\key_full_information.htm
old-project: kernel
ms.assetid: dd099435-e3e3-4d78-a829-0f12f2db46d9
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PKEY_FULL_INFORMATION, KEY_FULL_INFORMATION, KEY_FULL_INFORMATION structure [Kernel-Mode Driver Architecture], PKEY_FULL_INFORMATION, PKEY_FULL_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _KEY_FULL_INFORMATION, kernel.key_full_information, kstruct_c_1b9700b5-eedf-4f0f-8b73-bf4b9cfa0ccd.xml, wdm/KEY_FULL_INFORMATION, wdm/PKEY_FULL_INFORMATION"
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	KEY_FULL_INFORMATION
product: Windows
targetos: Windows
req.typenames: KEY_FULL_INFORMATION, *PKEY_FULL_INFORMATION
req.product: Windows 10 or later.
---

# _KEY_FULL_INFORMATION structure


## -description


The <b>KEY_FULL_INFORMATION</b> structure defines the information available for a registry key, including information about its subkeys and the maximum length for their names and value entries. This information can be used to size buffers to get the names of subkeys and their value entries.


## -struct-fields




### -field LastWriteTime

The last time this key or any of its values changed. This time value is expressed in absolute system time format. Absolute system time is the number of 100-nanosecond intervals since the start of the year 1601 in the Gregorian calendar.


### -field TitleIndex

Device and intermediate drivers should ignore this member.


### -field ClassOffset

The byte offset from the start of this structure to the <b>Class</b> member.


### -field ClassLength

The size, in bytes, of the key class name string in the <b>Class</b> array.


### -field SubKeys

The number of subkeys for this key.


### -field MaxNameLen

The maximum size, in bytes, of any name for a subkey.


### -field MaxClassLen

The maximum size, in bytes, of a class name.


### -field Values

The number of value entries for this key.


### -field MaxValueNameLen

The maximum size, in bytes, of a value entry name.


### -field MaxValueDataLen

The maximum size, in bytes, of a value entry data field.


### -field Class

An array of wide characters that contains the name of the class of the key. This character string is <u>not</u> null-terminated. Only the first element in this array is included in the <b>KEY_FULL_INFORMATION</b> structure definition. The storage for the remaining elements in the array immediately follows this element.


## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/ff566447">ZwEnumerateKey</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff567060">ZwQueryKey</a> routines use the <b>KEY_FULL_INFORMATION</b> structure to contain the full information for a registry key. When the <i>KeyInformationClass</i> parameter of either routine is <b>KeyFullInformation</b>, the <i>KeyInformation</i> buffer is treated as a <b>KEY_FULL_INFORMATION</b> structure.  For more information about the <b>KeyFullInformation</b> enumeration value, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff553373">KEY_INFORMATION_CLASS</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553355">KEY_BASIC_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553358">KEY_CACHED_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553373">KEY_INFORMATION_CLASS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553381">KEY_NAME_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553392">KEY_NODE_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554221">KEY_VIRTUALIZATION_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566447">ZwEnumerateKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567060">ZwQueryKey</a>
 

 

