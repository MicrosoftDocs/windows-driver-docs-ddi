---
UID: NS:ntddk._KEY_NAME_INFORMATION
title: "_KEY_NAME_INFORMATION"
author: windows-driver-content
description: The KEY_NAME_INFORMATION structure holds the name and name length of the key.
old-location: kernel\key_name_information.htm
tech.root: kernel
ms.assetid: 5b46e7d9-fbb0-4e55-b1f5-d9d0f1dd1f2c
ms.date: 04/30/2018
ms.keywords: "*PKEY_NAME_INFORMATION, KEY_NAME_INFORMATION, KEY_NAME_INFORMATION structure [Kernel-Mode Driver Architecture], PKEY_NAME_INFORMATION, PKEY_NAME_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _KEY_NAME_INFORMATION, kernel.key_name_information, kstruct_c_1b3b2976-9298-4d7d-a3d7-b0c8d303d29a.xml, ntddk/KEY_NAME_INFORMATION, ntddk/PKEY_NAME_INFORMATION"
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
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
-	Ntddk.h
api_name:
-	KEY_NAME_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: KEY_NAME_INFORMATION, *PKEY_NAME_INFORMATION
---

# _KEY_NAME_INFORMATION structure


## -description


The <b>KEY_NAME_INFORMATION</b> structure holds the name and name length of the key.


## -struct-fields




### -field NameLength

The size, in bytes, of the key name string in the <b>Name</b> array.


### -field Name

An array of wide characters that contains the name of the key. This character string is <u>not</u> null-terminated. Only the first element in this array is included in the <b>KEY_NAME_INFORMATION</b> structure definition. The storage for the remaining elements in the array immediately follows this element.


## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/ff567060">ZwQueryKey</a> routine uses the <b>KEY_NAME_INFORMATION</b> structure to contain the registry key name. When the <i>KeyInformationClass</i> parameter of this routine is <b>KeyNameInformation</b>, the <i>KeyInformation</i> buffer is treated as a <b>KEY_NAME_INFORMATION</b> structure.  For more information about the <b>KeyNameInformation</b> enumeration value, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff553373">KEY_INFORMATION_CLASS</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553355">KEY_BASIC_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553358">KEY_CACHED_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553373">KEY_INFORMATION_CLASS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553392">KEY_NODE_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554221">KEY_VIRTUALIZATION_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567060">ZwQueryKey</a>
 

 

