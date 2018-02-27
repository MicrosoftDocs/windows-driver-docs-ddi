---
UID: NS:wdm._KEY_VALUE_ENTRY
title: "_KEY_VALUE_ENTRY"
author: windows-driver-content
description: The KEY_VALUE_ENTRY structure is used by the REG_QUERY_MULTIPLE_VALUE_KEY_INFORMATION structure to describe a single value entry for a registry key.
old-location: kernel\key_value_entry.htm
old-project: kernel
ms.assetid: 8a0e819e-6da7-4006-a276-9bfd324800d8
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PKEY_VALUE_ENTRY, KEY_VALUE_ENTRY, KEY_VALUE_ENTRY structure [Kernel-Mode Driver Architecture], PKEY_VALUE_ENTRY, PKEY_VALUE_ENTRY structure pointer [Kernel-Mode Driver Architecture], _KEY_VALUE_ENTRY, kernel.key_value_entry, kstruct_c_750eac86-0e41-4623-8404-8c198c1ee96c.xml, wdm/KEY_VALUE_ENTRY, wdm/PKEY_VALUE_ENTRY"
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
-	KEY_VALUE_ENTRY
product: Windows
targetos: Windows
req.typenames: KEY_VALUE_ENTRY, *PKEY_VALUE_ENTRY
req.product: Windows 10 or later.
---

# _KEY_VALUE_ENTRY structure


## -description


The <b>KEY_VALUE_ENTRY</b> structure is used by the <a href="..\wdm\ns-wdm-_reg_query_multiple_value_key_information.md">REG_QUERY_MULTIPLE_VALUE_KEY_INFORMATION</a> structure to describe a single value entry for a registry key.


## -syntax


````
typedef struct _KEY_VALUE_ENTRY {
  PUNICODE_STRING ValueName;
  ULONG           DataLength;
  ULONG           DataOffset;
  ULONG           Type;
} KEY_VALUE_ENTRY, *PKEY_VALUE_ENTRY;
````


## -struct-fields




### -field ValueName

Pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that contains the name of the value entry.


### -field DataLength

Specifies the size, in bytes, of the data for the value entry.


### -field DataOffset

Specifies the offset, in bytes, of the value entry's data within the buffer that is pointed to by the <b>ValueBuffer</b> member of <a href="..\wdm\ns-wdm-_reg_query_multiple_value_key_information.md">REG_QUERY_MULTIPLE_VALUE_KEY_INFORMATION</a>.


### -field Type

Specifies the type of the value entry's data. For a description of the possible values for <b>Type</b>, see the <i>Type</i> parameter of <a href="..\wdm\nf-wdm-zwsetvaluekey.md">ZwSetValueKey</a>.


## -remarks



The <b>ValueEntries</b> member of <a href="..\wdm\ns-wdm-_reg_query_multiple_value_key_information.md">REG_QUERY_MULTIPLE_VALUE_KEY_INFORMATION</a> points to an array of KEY_VALUE_ENTRY structures.




## -see-also

<a href="..\wdm\ns-wdm-_reg_query_multiple_value_key_information.md">REG_QUERY_MULTIPLE_VALUE_KEY_INFORMATION</a>



<a href="..\wdm\nf-wdm-zwsetvaluekey.md">ZwSetValueKey</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KEY_VALUE_ENTRY structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

