---
UID: NS:wdm._KEY_VALUE_PARTIAL_INFORMATION
title: "_KEY_VALUE_PARTIAL_INFORMATION"
author: windows-driver-content
description: The KEY_VALUE_PARTIAL_INFORMATION structure defines a subset of the value information available for a value entry of a registry key.
old-location: kernel\key_value_partial_information.htm
old-project: kernel
ms.assetid: 8f8fc935-3d60-4159-8928-006b0b6c0b3d
ms.author: windowsdriverdev
ms.date: 2/24/2018
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdm.h
apiname:
-	KEY_VALUE_PARTIAL_INFORMATION
product: Windows
targetos: Windows
req.typenames: KEY_VALUE_PARTIAL_INFORMATION, *PKEY_VALUE_PARTIAL_INFORMATION
req.product: Windows 10 or later.
---

# _KEY_VALUE_PARTIAL_INFORMATION structure


## -description


The <b>KEY_VALUE_PARTIAL_INFORMATION</b> structure defines a subset of the value information available for a value entry of a registry key.


## -syntax


````
typedef struct _KEY_VALUE_PARTIAL_INFORMATION {
  ULONG TitleIndex;
  ULONG Type;
  ULONG DataLength;
  UCHAR Data[1];
} KEY_VALUE_PARTIAL_INFORMATION, *PKEY_VALUE_PARTIAL_INFORMATION;
````


## -struct-fields




### -field TitleIndex

Device and intermediate drivers should ignore this member.


### -field Type

Specifies the system-defined type for the registry value in the <b>Data</b> member. For a summary of these types, see <a href="..\wdm\ns-wdm-_key_value_basic_information.md">KEY_VALUE_BASIC_INFORMATION</a>.


### -field DataLength

The size in bytes of the <b>Data</b> member.


### -field Data

A value entry of the key.


## -see-also

<a href="..\wdm\nf-wdm-zwenumeratevaluekey.md">ZwEnumerateValueKey</a>



<a href="..\wdm\ne-wdm-_key_value_information_class.md">KEY_VALUE_INFORMATION_CLASS</a>



<a href="..\wdm\ns-wdm-_key_value_basic_information.md">KEY_VALUE_BASIC_INFORMATION</a>



<a href="..\wdm\ns-wdm-_key_value_full_information.md">KEY_VALUE_FULL_INFORMATION</a>



<a href="..\wdm\nf-wdm-zwqueryvaluekey.md">ZwQueryValueKey</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KEY_VALUE_PARTIAL_INFORMATION structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

