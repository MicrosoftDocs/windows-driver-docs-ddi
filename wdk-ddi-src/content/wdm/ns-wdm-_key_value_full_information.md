---
UID: NS:wdm._KEY_VALUE_FULL_INFORMATION
title: "_KEY_VALUE_FULL_INFORMATION"
author: windows-driver-content
description: The KEY_VALUE_FULL_INFORMATION structure defines information available for a value entry of a registry key.
old-location: kernel\key_value_full_information.htm
old-project: kernel
ms.assetid: 0340cfa7-957d-4404-8dbd-d3178436de0f
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PKEY_VALUE_FULL_INFORMATION, KEY_VALUE_FULL_INFORMATION, KEY_VALUE_FULL_INFORMATION structure [Kernel-Mode Driver Architecture], PKEY_VALUE_FULL_INFORMATION, PKEY_VALUE_FULL_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _KEY_VALUE_FULL_INFORMATION, kernel.key_value_full_information, kstruct_c_15c88f03-6342-40db-9f43-cb4087f24610.xml, wdm/KEY_VALUE_FULL_INFORMATION, wdm/PKEY_VALUE_FULL_INFORMATION"
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
-	wdm.h
api_name:
-	KEY_VALUE_FULL_INFORMATION
product: Windows
targetos: Windows
req.typenames: KEY_VALUE_FULL_INFORMATION, *PKEY_VALUE_FULL_INFORMATION
req.product: Windows 10 or later.
---

# _KEY_VALUE_FULL_INFORMATION structure


## -description


The <b>KEY_VALUE_FULL_INFORMATION</b> structure defines information available for a value entry of a registry key.


## -struct-fields




### -field TitleIndex

Device and intermediate drivers should ignore this member. 


### -field Type

Specifies the system-defined type for the registry value(s) following the <b>Name</b> member. For a summary of these types, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff553410">KEY_VALUE_BASIC_INFORMATION</a>.


### -field DataOffset

Specifies the offset from the start of this structure to the data immediately following the <b>Name</b> string.


### -field DataLength

Specifies the number of bytes of registry information for the value entry identified by <b>Name</b>.


### -field NameLength

Specifies the size in bytes of the following value entry name. 


### -field Name

A string of Unicode characters naming a value entry of the key. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553410">KEY_VALUE_BASIC_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554218">KEY_VALUE_INFORMATION_CLASS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554220">KEY_VALUE_PARTIAL_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566453">ZwEnumerateValueKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567069">ZwQueryValueKey</a>
 

 

