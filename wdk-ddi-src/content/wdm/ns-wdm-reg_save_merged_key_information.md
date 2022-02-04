---
UID: NS:wdm._REG_SAVE_MERGED_KEY_INFORMATION
tech.root: kernel
title: REG_SAVE_MERGED_KEY_INFORMATION
ms.date: 01/31/2022
targetos: Windows
description: Defines the REG_SAVE_MERGED_KEY_INFORMATION structure.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.include-header: Wdm.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: REG_SAVE_MERGED_KEY_INFORMATION, *PREG_SAVE_MERGED_KEY_INFORMATION
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _REG_SAVE_MERGED_KEY_INFORMATION
 - PREG_SAVE_MERGED_KEY_INFORMATION
 - REG_SAVE_MERGED_KEY_INFORMATION
f1_keywords:
 - _REG_SAVE_MERGED_KEY_INFORMATION
 - wdm/_REG_SAVE_MERGED_KEY_INFORMATION
 - PREG_SAVE_MERGED_KEY_INFORMATION
 - wdm/PREG_SAVE_MERGED_KEY_INFORMATION
 - REG_SAVE_MERGED_KEY_INFORMATION
 - wdm/REG_SAVE_MERGED_KEY_INFORMATION
dev_langs:
 - c++
---

## -description

The **REG_SAVE_MERGED_KEY_INFORMATION** structure contains the information about the two registry subtrees, who's merged view is expected to be saved to a file.

## -struct-fields

### -field Object

NULL

### -field FileHandle

Supplies a file handle with write access to the target file.

### -field HighKeyObject

Supplies a pointer to the registry key object that represents the root of the higher precedence tree. When a key is present in both the trees headed by the two keys, the key underneath HighPrecendence tree will always prevail. The specified node will be included in the data written out.

### -field LowKeyObject

Supplies a pointer to the registry key object that represents the root of the "second choice" tree. Keys from this tree gets saved when there is no equivalent key in the tree headed by HighPrecedence key.

### -field CallContext

Optional driver-defined context information that the driver's RegistryCallback routine can supply. This member is defined for Windows Vista and later versions of the Windows operating system.

### -field ObjectContext

A pointer to driver-defined context information that the driver has associated with a registry object by calling CmSetCallbackObjectContext. This member is defined for Windows Vista and later versions of the Windows operating system.

### -field Reserved

This member is reserved for future use. This member is defined for Windows Vista and later versions of the Windows operating system.

## -remarks

The system passes this structure to the <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a> routine every time a thread attempts to save merged view of two registry subtrees to a file using ZwSaveMergedKeys.

For more information about registry filtering operations, see <a href="/windows-hardware/drivers/kernel/filtering-registry-calls">Filtering Registry Calls</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-cmsetcallbackobjectcontext">CmSetCallbackObjectContext</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a>

<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">EX_CALLBACK_FUNCTION</a>


<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-reg_save_merged_key_information">REG_SAVE_MERGED_KEY_INFORMATION</a>
