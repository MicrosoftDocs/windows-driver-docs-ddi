---
UID: NS:wdm._KEY_VALUE_PARTIAL_INFORMATION
title: "_KEY_VALUE_PARTIAL_INFORMATION"
author: windows-driver-content
description: The KEY_VALUE_PARTIAL_INFORMATION structure defines a subset of the value information available for a value entry of a registry key.
old-location: kernel\key_value_partial_information.htm
old-project: kernel
ms.assetid: 8f8fc935-3d60-4159-8928-006b0b6c0b3d
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PKEY_VALUE_PARTIAL_INFORMATION, KEY_VALUE_PARTIAL_INFORMATION, KEY_VALUE_PARTIAL_INFORMATION structure [Kernel-Mode Driver Architecture], PKEY_VALUE_PARTIAL_INFORMATION, PKEY_VALUE_PARTIAL_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _KEY_VALUE_PARTIAL_INFORMATION, kernel.key_value_partial_information, kstruct_c_d96b4d6b-abe9-4ac0-af16-80c7edd25df8.xml, wdm/KEY_VALUE_PARTIAL_INFORMATION, wdm/PKEY_VALUE_PARTIAL_INFORMATION"
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
-	KEY_VALUE_PARTIAL_INFORMATION
product: Windows
targetos: Windows
req.typenames: KEY_VALUE_PARTIAL_INFORMATION, *PKEY_VALUE_PARTIAL_INFORMATION
req.product: Windows 10 or later.
---

# _KEY_VALUE_PARTIAL_INFORMATION structure


## -description


The <b>KEY_VALUE_PARTIAL_INFORMATION</b> structure defines a subset of the value information available for a value entry of a registry key.


## -struct-fields




### -field TitleIndex

Device and intermediate drivers should ignore this member.


### -field Type

Specifies the system-defined type for the registry value in the <b>Data</b> member. For a summary of these types, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff553410">KEY_VALUE_BASIC_INFORMATION</a>.


### -field DataLength

The size in bytes of the <b>Data</b> member.


### -field Data

A value entry of the key.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553410">KEY_VALUE_BASIC_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554217">KEY_VALUE_FULL_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554218">KEY_VALUE_INFORMATION_CLASS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566453">ZwEnumerateValueKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567069">ZwQueryValueKey</a>
 

 

