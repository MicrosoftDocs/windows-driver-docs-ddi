---
UID: NS:ntddk._KEY_NAME_INFORMATION
title: "_KEY_NAME_INFORMATION"
author: windows-driver-content
description: The KEY_NAME_INFORMATION structure holds the name and name length of the key.
old-location: kernel\key_name_information.htm
old-project: kernel
ms.assetid: 5b46e7d9-fbb0-4e55-b1f5-d9d0f1dd1f2c
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PKEY_NAME_INFORMATION, KEY_NAME_INFORMATION, KEY_NAME_INFORMATION structure [Kernel-Mode Driver Architecture], PKEY_NAME_INFORMATION, PKEY_NAME_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _KEY_NAME_INFORMATION, kernel.key_name_information, kstruct_c_1b3b2976-9298-4d7d-a3d7-b0c8d303d29a.xml, ntddk/KEY_NAME_INFORMATION, ntddk/PKEY_NAME_INFORMATION"
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddk.h
api_name:
-	KEY_NAME_INFORMATION
product: Windows
targetos: Windows
req.typenames: KEY_NAME_INFORMATION, *PKEY_NAME_INFORMATION
---

# _KEY_NAME_INFORMATION structure


## -description


The <b>KEY_NAME_INFORMATION</b> structure holds the name and name length of the key.


## -syntax


````
typedef struct _KEY_NAME_INFORMATION {
  ULONG NameLength;
  WCHAR Name[1];
} KEY_NAME_INFORMATION, *PKEY_NAME_INFORMATION;
````


## -struct-fields




### -field NameLength

The size, in bytes, of the key name string in the <b>Name</b> array.


### -field Name

An array of wide characters that contains the name of the key. This character string is <u>not</u> null-terminated. Only the first element in this array is included in the <b>KEY_NAME_INFORMATION</b> structure definition. The storage for the remaining elements in the array immediately follows this element.


## -remarks



The <a href="..\wdm\nf-wdm-zwquerykey.md">ZwQueryKey</a> routine uses the <b>KEY_NAME_INFORMATION</b> structure to contain the registry key name. When the <i>KeyInformationClass</i> parameter of this routine is <b>KeyNameInformation</b>, the <i>KeyInformation</i> buffer is treated as a <b>KEY_NAME_INFORMATION</b> structure.  For more information about the <b>KeyNameInformation</b> enumeration value, see <a href="..\wdm\ne-wdm-_key_information_class.md">KEY_INFORMATION_CLASS</a>.




## -see-also

<a href="..\wdm\ns-wdm-_key_basic_information.md">KEY_BASIC_INFORMATION</a>



<a href="..\ntddk\ns-ntddk-_key_virtualization_information.md">KEY_VIRTUALIZATION_INFORMATION</a>



<a href="..\wdm\ns-wdm-_key_node_information.md">KEY_NODE_INFORMATION</a>



<a href="..\ntddk\ns-ntddk-_key_cached_information.md">KEY_CACHED_INFORMATION</a>



<a href="..\wdm\ne-wdm-_key_information_class.md">KEY_INFORMATION_CLASS</a>



<a href="..\wdm\nf-wdm-zwquerykey.md">ZwQueryKey</a>



 

 


