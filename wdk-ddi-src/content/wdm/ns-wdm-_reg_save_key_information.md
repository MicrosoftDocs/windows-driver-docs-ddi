---
UID: NS:wdm._REG_SAVE_KEY_INFORMATION
title: _REG_SAVE_KEY_INFORMATION (wdm.h)
description: The REG_SAVE_KEY_INFORMATION structure contains the information for a registry key that is about to be saved.
old-location: kernel\reg_save_key_information.htm
tech.root: kernel
ms.assetid: 911e1035-4415-43c1-9e9c-cc8feab2bd97
ms.date: 04/30/2018
keywords: ["REG_SAVE_KEY_INFORMATION structure"]
ms.keywords: "*PREG_SAVE_KEY_INFORMATION, PREG_SAVE_KEY_INFORMATION, PREG_SAVE_KEY_INFORMATION structure pointer [Kernel-Mode Driver Architecture], REG_SAVE_KEY_INFORMATION, REG_SAVE_KEY_INFORMATION structure [Kernel-Mode Driver Architecture], _REG_SAVE_KEY_INFORMATION, kernel.reg_save_key_information, kstruct_d_7da1ebfa-ae75-4b84-8941-87004f965404.xml, wdm/PREG_SAVE_KEY_INFORMATION, wdm/REG_SAVE_KEY_INFORMATION"
f1_keywords:
 - "wdm/REG_SAVE_KEY_INFORMATION"
 - "REG_SAVE_KEY_INFORMATION"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wdm.h
api_name:
- REG_SAVE_KEY_INFORMATION
targetos: Windows
req.typenames: REG_SAVE_KEY_INFORMATION, *PREG_SAVE_KEY_INFORMATION
---

# _REG_SAVE_KEY_INFORMATION structure


## -description


The <b>REG_SAVE_KEY_INFORMATION</b> structure contains the information for a registry key that is about to be saved.


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

Optional driver-defined context information that the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a> routine can supply. This member is defined starting with Windows Vista.


### -field ObjectContext

A pointer to driver-defined context information, which the driver has associated with a registry object by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-cmsetcallbackobjectcontext">CmSetCallbackObjectContext</a>. This member is defined starting with Windows Vista.


### -field Reserved

This member is reserved for future use. This member is defined starting with Windows Vista.


## -remarks



Note that when a key is saved, only the last component of the path can be changed.

For more information about registry filtering operations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/filtering-registry-calls">Filtering Registry Calls</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-cmsetcallbackobjectcontext">CmSetCallbackObjectContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a>
 

 

