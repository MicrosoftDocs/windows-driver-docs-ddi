---
UID: NS:wdm._REG_PRE_CREATE_KEY_INFORMATION
title: _REG_PRE_CREATE_KEY_INFORMATION (wdm.h)
description: The REG_PRE_OPEN_KEY_INFORMATION structure contains the name of a registry key that is about to be opened.
old-location: kernel\reg_pre_open_key_information.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["REG_PRE_CREATE_KEY_INFORMATION structure"]
ms.keywords: "*PREG_PRE_CREATE_KEY_INFORMATION, *PREG_PRE_OPEN_KEY_INFORMATION, PREG_PRE_CREATE_KEY_INFORMATION, PREG_PRE_CREATE_KEY_INFORMATION structure pointer [Kernel-Mode Driver Architecture], REG_PRE_CREATE_KEY_INFORMATION, REG_PRE_CREATE_KEY_INFORMATION structure [Kernel-Mode Driver Architecture], REG_PRE_OPEN_KEY_INFORMATION, REG_PRE_OPEN_KEY_INFORMATION structure [Kernel-Mode Driver Architecture], _REG_PRE_CREATE_KEY_INFORMATION, kernel.reg_pre_open_key_information, kstruct_d_dc0e8cf3-5084-4d54-8767-50b4ff043da8.xml, wdm/PREG_PRE_CREATE_KEY_INFORMATION, wdm/REG_PRE_CREATE_KEY_INFORMATION, wdm/REG_PRE_OPEN_KEY_INFORMATION"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available only on Microsoft Windows XP.
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
req.typenames: REG_PRE_CREATE_KEY_INFORMATION, REG_PRE_OPEN_KEY_INFORMATION, *PREG_PRE_CREATE_KEY_INFORMATION, *PREG_PRE_OPEN_KEY_INFORMATION
f1_keywords:
 - _REG_PRE_CREATE_KEY_INFORMATION
 - wdm/_REG_PRE_CREATE_KEY_INFORMATION
 - PREG_PRE_CREATE_KEY_INFORMATION
 - wdm/PREG_PRE_CREATE_KEY_INFORMATION
 - REG_PRE_CREATE_KEY_INFORMATION
 - wdm/REG_PRE_CREATE_KEY_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - REG_PRE_CREATE_KEY_INFORMATION
---

# _REG_PRE_CREATE_KEY_INFORMATION structure


## -description

The <b>REG_PRE_OPEN_KEY_INFORMATION</b> structure contains the name of a registry key that is about to be opened.

## -struct-fields

### -field CompleteName

A pointer to a <a href="/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that contains the complete path of the registry key.

## -remarks

For more information about registry filtering operations, see <a href="/windows-hardware/drivers/kernel/filtering-registry-calls">Filtering Registry Calls</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a>



<a href="/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwopenkey">ZwOpenKey</a>
