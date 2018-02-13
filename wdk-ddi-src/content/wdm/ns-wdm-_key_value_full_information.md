---
UID: NS:wdm._KEY_VALUE_FULL_INFORMATION
title: "_KEY_VALUE_FULL_INFORMATION"
author: windows-driver-content
description: The KEY_VALUE_FULL_INFORMATION structure defines information available for a value entry of a registry key.
old-location: kernel\key_value_full_information.htm
old-project: kernel
ms.assetid: 0340cfa7-957d-4404-8dbd-d3178436de0f
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.key_value_full_information, PKEY_VALUE_FULL_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _KEY_VALUE_FULL_INFORMATION, wdm/PKEY_VALUE_FULL_INFORMATION, kstruct_c_15c88f03-6342-40db-9f43-cb4087f24610.xml, *PKEY_VALUE_FULL_INFORMATION, PKEY_VALUE_FULL_INFORMATION, wdm/KEY_VALUE_FULL_INFORMATION, KEY_VALUE_FULL_INFORMATION, KEY_VALUE_FULL_INFORMATION structure [Kernel-Mode Driver Architecture]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdm.h
apiname:
-	KEY_VALUE_FULL_INFORMATION
product: Windows
targetos: Windows
req.typenames: "*PKEY_VALUE_FULL_INFORMATION, KEY_VALUE_FULL_INFORMATION"
req.product: Windows 10 or later.
---

# _KEY_VALUE_FULL_INFORMATION structure


## -description


The <b>KEY_VALUE_FULL_INFORMATION</b> structure defines information available for a value entry of a registry key.


## -syntax


````
typedef struct _KEY_VALUE_FULL_INFORMATION {
  ULONG TitleIndex;
  ULONG Type;
  ULONG DataOffset;
  ULONG DataLength;
  ULONG NameLength;
  WCHAR Name[1];
} KEY_VALUE_FULL_INFORMATION, *PKEY_VALUE_FULL_INFORMATION;
````


## -struct-fields




### -field TitleIndex

Device and intermediate drivers should ignore this member. 


### -field Type

Specifies the system-defined type for the registry value(s) following the <b>Name</b> member. For a summary of these types, see <a href="..\wdm\ns-wdm-_key_value_basic_information.md">KEY_VALUE_BASIC_INFORMATION</a>.


### -field DataOffset

Specifies the offset from the start of this structure to the data immediately following the <b>Name</b> string.


### -field DataLength

Specifies the number of bytes of registry information for the value entry identified by <b>Name</b>.


### -field NameLength

Specifies the size in bytes of the following value entry name. 


### -field Name

A string of Unicode characters naming a value entry of the key. 


## -see-also

<a href="..\wdm\ns-wdm-_key_value_partial_information.md">KEY_VALUE_PARTIAL_INFORMATION</a>



<a href="..\wdm\nf-wdm-zwenumeratevaluekey.md">ZwEnumerateValueKey</a>



<a href="..\wdm\ne-wdm-_key_value_information_class.md">KEY_VALUE_INFORMATION_CLASS</a>



<a href="..\wdm\ns-wdm-_key_value_basic_information.md">KEY_VALUE_BASIC_INFORMATION</a>



<a href="..\wdm\nf-wdm-zwqueryvaluekey.md">ZwQueryValueKey</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KEY_VALUE_FULL_INFORMATION structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

