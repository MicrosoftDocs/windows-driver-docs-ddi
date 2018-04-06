---
UID: NS:wdm._KEY_NODE_INFORMATION
title: "_KEY_NODE_INFORMATION"
author: windows-driver-content
description: The KEY_NODE_INFORMATION structure defines the basic information available for a registry (sub)key.
old-location: kernel\key_node_information.htm
old-project: kernel
ms.assetid: 2eed1a3d-fc40-4416-ad61-d82bf4fb69a1
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PKEY_NODE_INFORMATION, KEY_NODE_INFORMATION, KEY_NODE_INFORMATION structure [Kernel-Mode Driver Architecture], PKEY_NODE_INFORMATION, PKEY_NODE_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _KEY_NODE_INFORMATION, kernel.key_node_information, kstruct_c_a41bb6c8-4e12-4aac-94cf-a24d32727c5e.xml, wdm/KEY_NODE_INFORMATION, wdm/PKEY_NODE_INFORMATION"
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
-	KEY_NODE_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: KEY_NODE_INFORMATION, *PKEY_NODE_INFORMATION
req.product: Windows 10 or later.
---

# _KEY_NODE_INFORMATION structure


## -description


The <b>KEY_NODE_INFORMATION</b> structure defines the basic information available for a registry (sub)key.


## -struct-fields




### -field LastWriteTime

The last time this key or any of its values changed. This time value is expressed in absolute system time format. Absolute system time is the number of 100-nanosecond intervals since the start of the year 1601 in the Gregorian calendar.


### -field TitleIndex

Device and intermediate drivers should ignore this member.


### -field ClassOffset

The byte offset from the start of this structure to the class name string, which is located in the <b>Name</b> array immediately following the key name string. Like the key name string, the class name string is not null-terminated.


### -field ClassLength

The size, in bytes, in the class name string.


### -field NameLength

The size, in bytes, of the key name string contained in the <b>Name</b> array.


### -field Name

An array of wide characters that contains the name of the registry key. This character string is <u>not</u> null-terminated. Only the first element in this array is included in the <b>KEY_NODE_INFORMATION</b> structure definition. The storage for the remaining elements in the array immediately follows this element.


## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/ff566447">ZwEnumerateKey</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff567060">ZwQueryKey</a> routines use the <b>KEY_NODE_INFORMATION</b> structure to contain the registry key name and key class name. When the <i>KeyInformationClass</i> parameter of either routine is <b>KeyNodeInformation</b>, the <i>KeyInformation</i> buffer is treated as a <b>KEY_NODE_INFORMATION</b> structure. For more information about the <b>KeyNodeInformation</b> enumeration value, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff553373">KEY_INFORMATION_CLASS</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553355">KEY_BASIC_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553358">KEY_CACHED_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553367">KEY_FULL_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553373">KEY_INFORMATION_CLASS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553381">KEY_NAME_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554221">KEY_VIRTUALIZATION_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566447">ZwEnumerateKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567060">ZwQueryKey</a>
 

 

