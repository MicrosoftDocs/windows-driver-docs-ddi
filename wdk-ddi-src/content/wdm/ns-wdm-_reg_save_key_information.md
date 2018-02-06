---
UID: NS:wdm._REG_SAVE_KEY_INFORMATION
title: "_REG_SAVE_KEY_INFORMATION"
author: windows-driver-content
description: The REG_SAVE_KEY_INFORMATION structure contains the information for a registry key that is about to be saved.
old-location: kernel\reg_save_key_information.htm
old-project: kernel
ms.assetid: 911e1035-4415-43c1-9e9c-cc8feab2bd97
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: REG_SAVE_KEY_INFORMATION, wdm/PREG_SAVE_KEY_INFORMATION, REG_SAVE_KEY_INFORMATION structure [Kernel-Mode Driver Architecture], kernel.reg_save_key_information, wdm/REG_SAVE_KEY_INFORMATION, PREG_SAVE_KEY_INFORMATION, _REG_SAVE_KEY_INFORMATION, kstruct_d_7da1ebfa-ae75-4b84-8941-87004f965404.xml, PREG_SAVE_KEY_INFORMATION structure pointer [Kernel-Mode Driver Architecture], *PREG_SAVE_KEY_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista SP2.
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
-	Wdm.h
apiname:
-	REG_SAVE_KEY_INFORMATION
product: Windows
targetos: Windows
req.typenames: "*PREG_SAVE_KEY_INFORMATION, REG_SAVE_KEY_INFORMATION"
req.product: Windows 10 or later.
---

# _REG_SAVE_KEY_INFORMATION structure


## -description


The <b>REG_SAVE_KEY_INFORMATION</b> structure contains the information for a registry key that is about to be saved.


## -syntax


````
typedef struct _REG_SAVE_KEY_INFORMATION {
  PVOID  Object;
  HANDLE FileHandle;
  ULONG  Format;
  PVOID  CallContext;
  PVOID  ObjectContext;
  PVOID  Reserved;
} REG_SAVE_KEY_INFORMATION, *PREG_SAVE_KEY_INFORMATION;
````


## -struct-fields




### -field Object

A pointer to a registry key object for the key whose information is about to be saved.


### -field FileHandle

A handle to the file to which the hive information will be saved.


### -field Format

The format in which the key or hive is saved. This member can have one of the following values.
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>REG_STANDARD_FORMAT</td>
<td>Save in standard format. The standard format is the only format supported by Windows 2000.</td>
</tr>
<tr>
<td>REG_LATEST_FORMAT</td>
<td>Save in the latest format. The latest format is supported starting with Windows XP. After the key is saved in this format, it cannot be loaded on an earlier version of Windows.</td>
</tr>
<tr>
<td>REG_NO_COMPRESSION</td>
<td>Save with no compression, for faster save operations. The registry key object must represent the root of a hive.</td>
</tr>
</table> 


### -field CallContext

Optional driver-defined context information that the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine can supply. This member is defined starting with Windows Vista.


### -field ObjectContext

A pointer to driver-defined context information, which the driver has associated with a registry object by calling <a href="..\wdm\nf-wdm-cmsetcallbackobjectcontext.md">CmSetCallbackObjectContext</a>. This member is defined starting with Windows Vista.


### -field Reserved

This member is reserved for future use. This member is defined starting with Windows Vista.


## -remarks


Note that when a key is saved, only the last component of the path can be changed.

For more information about registry filtering operations, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545879">Filtering Registry Calls</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a>

<a href="..\wdm\nf-wdm-cmsetcallbackobjectcontext.md">CmSetCallbackObjectContext</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20REG_SAVE_KEY_INFORMATION structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

