---
UID: NS:wdm._REG_QUERY_MULTIPLE_VALUE_KEY_INFORMATION
title: _REG_QUERY_MULTIPLE_VALUE_KEY_INFORMATION (wdm.h)
description: The REG_QUERY_MULTIPLE_VALUE_KEY_INFORMATION structure describes the multiple value entries that are being retrieved for a key.
old-location: kernel\reg_query_multiple_value_key_information.htm
tech.root: kernel
ms.assetid: 764045c0-9057-4abc-a1bd-8713797082c6
ms.date: 04/30/2018
ms.keywords: "*PREG_QUERY_MULTIPLE_VALUE_KEY_INFORMATION, PREG_QUERY_MULTIPLE_VALUE_KEY_INFORMATION, PREG_QUERY_MULTIPLE_VALUE_KEY_INFORMATION structure pointer [Kernel-Mode Driver Architecture], REG_QUERY_MULTIPLE_VALUE_KEY_INFORMATION, REG_QUERY_MULTIPLE_VALUE_KEY_INFORMATION structure [Kernel-Mode Driver Architecture], _REG_QUERY_MULTIPLE_VALUE_KEY_INFORMATION, kernel.reg_query_multiple_value_key_information, kstruct_d_b61ed5ad-3ac8-4db4-abe9-5670b4c8d997.xml, wdm/PREG_QUERY_MULTIPLE_VALUE_KEY_INFORMATION, wdm/REG_QUERY_MULTIPLE_VALUE_KEY_INFORMATION"
ms.topic: struct
f1_keywords:
 - "wdm/REG_QUERY_MULTIPLE_VALUE_KEY_INFORMATION"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdm.h
api_name:
- REG_QUERY_MULTIPLE_VALUE_KEY_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: REG_QUERY_MULTIPLE_VALUE_KEY_INFORMATION, *PREG_QUERY_MULTIPLE_VALUE_KEY_INFORMATION
---

# _REG_QUERY_MULTIPLE_VALUE_KEY_INFORMATION structure


## -description


The <b>REG_QUERY_MULTIPLE_VALUE_KEY_INFORMATION</b> structure describes the multiple value entries that are being retrieved for a key.


## -struct-fields




### -field Object

A pointer to the registry key object for the key whose value entries are being retrieved.


### -field ValueEntries

A pointer to an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_key_value_entry">KEY_VALUE_ENTRY</a> structures, one for each value entry that is retrieved.


### -field EntryCount

The number of entries in the <b>ValueEntries</b> array.


### -field ValueBuffer

A pointer to a buffer that receives (from the system) the data for all the value entries specified by the <b>ValueEntries</b> array.


### -field BufferLength

A pointer to a variable that contains the length, in bytes, of the <b>ValueBuffer</b> buffer.


### -field RequiredBufferLength

A pointer to a variable that receives (from the system) the number of bytes required to hold the data for all the value entries that the <b>ValueEntries</b> array specifies. This member can be <b>NULL</b>.


### -field CallContext

Optional driver-defined context information that the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-ex_callback_function">RegistryCallback</a> routine can supply. This member is defined for Windows Vista and later versions of the Windows operating system.


### -field ObjectContext

A pointer to driver-defined context information that the driver has associated with a registry object by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-cmsetcallbackobjectcontext">CmSetCallbackObjectContext</a>. This member is defined for Windows Vista and later versions of the Windows operating system.


### -field Reserved

This member is reserved for future use. This member is defined for Windows Vista and later versions of the Windows operating system.


## -remarks



The system passes this structure to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-ex_callback_function">RegistryCallback</a> routine every time a thread attempts to retrieve multiple value entries for a key at once—for example, when a user-mode thread calls <b>RegQueryMultipleValues</b>.

Each <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_key_value_entry">KEY_VALUE_ENTRY</a> structure in the <b>ValueEntries</b> array describes one value entry in the <b>ValueBuffer</b> buffer. Specifically, the <b>DataOffset</b> member of <b>KEY_VALUE_ENTRY</b> contains the offset within <b>ValueBuffer</b> where the data for that value entry begins, and the <b>DataLength</b> member contains the length, in bytes, of the data for that value entry.

For more information about registry filtering operations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/filtering-registry-calls">Filtering Registry Calls</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-cmsetcallbackobjectcontext">CmSetCallbackObjectContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_key_value_entry">KEY_VALUE_ENTRY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-ex_callback_function">RegistryCallback</a>
 

 

