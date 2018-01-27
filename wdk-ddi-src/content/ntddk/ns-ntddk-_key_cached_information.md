---
UID: NS:ntddk._KEY_CACHED_INFORMATION
title: _KEY_CACHED_INFORMATION
author: windows-driver-content
description: The KEY_CACHED_INFORMATION structure holds the cached information available for a registry key or subkey.
old-location: kernel\key_cached_information.htm
old-project: kernel
ms.assetid: 5ee72ae9-0548-480f-84de-4c09ae4be507
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ntddk/PKEY_CACHED_INFORMATION, PKEY_CACHED_INFORMATION, _KEY_CACHED_INFORMATION, KEY_CACHED_INFORMATION, ntddk/KEY_CACHED_INFORMATION, PKEY_CACHED_INFORMATION structure pointer [Kernel-Mode Driver Architecture], KEY_CACHED_INFORMATION structure [Kernel-Mode Driver Architecture], *PKEY_CACHED_INFORMATION, kstruct_c_72dd8fcc-4983-49e0-af00-57b8fbbf3964.xml, kernel.key_cached_information
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating system.
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	Ntddk.h
apiname: 
-	KEY_CACHED_INFORMATION
product: Windows
targetos: Windows
req.typenames: *PKEY_CACHED_INFORMATION, KEY_CACHED_INFORMATION
---

# _KEY_CACHED_INFORMATION structure


## -description


The <b>KEY_CACHED_INFORMATION</b> structure holds the cached information available for a registry key or subkey.


## -syntax


````
typedef struct _KEY_CACHED_INFORMATION {
  LARGE_INTEGER LastWriteTime;
  ULONG         TitleIndex;
  ULONG         SubKeys;
  ULONG         MaxNameLen;
  ULONG         Values;
  ULONG         MaxValueNameLen;
  ULONG         MaxValueDataLen;
  ULONG         NameLength;
} KEY_CACHED_INFORMATION, *PKEY_CACHED_INFORMATION;
````


## -struct-fields




### -field LastWriteTime

The last time the key or any of its values changed. This time value is expressed in absolute system time format. Absolute system time is the number of 100-nanosecond intervals since the start of the year 1601 in the Gregorian calendar.


### -field TitleIndex

Device and intermediate drivers should ignore this member.


### -field SubKeys

The number of subkeys for a key.


### -field MaxNameLen

The maximum number of bytes for a subkey name.


### -field Values

The number of value entries.


### -field MaxValueNameLen

The maximum length, in bytes, of any value entry name.


### -field MaxValueDataLen

The maximum length, in bytes, of a value entry data field.


### -field NameLength

The size, in bytes, of the key name.


## -see-also

<a href="..\ntddk\ns-ntddk-_key_name_information.md">KEY_NAME_INFORMATION</a>

<a href="..\wdm\ns-wdm-_key_full_information.md">KEY_FULL_INFORMATION</a>

<a href="..\wdm\ns-wdm-_key_node_information.md">KEY_NODE_INFORMATION</a>

<a href="..\wdm\ns-wdm-_key_basic_information.md">KEY_BASIC_INFORMATION</a>

<a href="..\wdm\ne-wdm-_key_information_class.md">KEY_INFORMATION_CLASS</a>

<a href="..\wdm\nf-wdm-zwquerykey.md">ZwQueryKey</a>

<a href="..\wdm\nf-wdm-zwenumeratekey.md">ZwEnumerateKey</a>

<a href="..\ntddk\ns-ntddk-_key_virtualization_information.md">KEY_VIRTUALIZATION_INFORMATION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KEY_CACHED_INFORMATION structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

