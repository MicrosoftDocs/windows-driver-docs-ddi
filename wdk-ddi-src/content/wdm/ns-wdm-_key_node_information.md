---
UID: NS:wdm._KEY_NODE_INFORMATION
title: _KEY_NODE_INFORMATION (wdm.h)
description: The KEY_NODE_INFORMATION structure defines the basic information available for a registry (sub)key.
old-location: kernel\key_node_information.htm
tech.root: kernel
ms.assetid: 2eed1a3d-fc40-4416-ad61-d82bf4fb69a1
ms.date: 04/30/2018
keywords: ["KEY_NODE_INFORMATION structure"]
ms.keywords: "*PKEY_NODE_INFORMATION, KEY_NODE_INFORMATION, KEY_NODE_INFORMATION structure [Kernel-Mode Driver Architecture], PKEY_NODE_INFORMATION, PKEY_NODE_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _KEY_NODE_INFORMATION, kernel.key_node_information, kstruct_c_a41bb6c8-4e12-4aac-94cf-a24d32727c5e.xml, wdm/KEY_NODE_INFORMATION, wdm/PKEY_NODE_INFORMATION"
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
targetos: Windows
req.typenames: KEY_NODE_INFORMATION, *PKEY_NODE_INFORMATION
f1_keywords:
 - _KEY_NODE_INFORMATION
 - wdm/_KEY_NODE_INFORMATION
 - PKEY_NODE_INFORMATION
 - wdm/PKEY_NODE_INFORMATION
 - KEY_NODE_INFORMATION
 - wdm/KEY_NODE_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - KEY_NODE_INFORMATION
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

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwenumeratekey">ZwEnumerateKey</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwquerykey">ZwQueryKey</a> routines use the <b>KEY_NODE_INFORMATION</b> structure to contain the registry key name and key class name. When the <i>KeyInformationClass</i> parameter of either routine is <b>KeyNodeInformation</b>, the <i>KeyInformation</i> buffer is treated as a <b>KEY_NODE_INFORMATION</b> structure. For more information about the <b>KeyNodeInformation</b> enumeration value, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_key_information_class">KEY_INFORMATION_CLASS</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_key_basic_information">KEY_BASIC_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_key_cached_information">KEY_CACHED_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_key_full_information">KEY_FULL_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_key_information_class">KEY_INFORMATION_CLASS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_key_name_information">KEY_NAME_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_key_virtualization_information">KEY_VIRTUALIZATION_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwenumeratekey">ZwEnumerateKey</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwquerykey">ZwQueryKey</a>

