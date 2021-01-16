---
UID: NE:wdm._KEY_SET_INFORMATION_CLASS
title: _KEY_SET_INFORMATION_CLASS (wdm.h)
description: The KEY_SET_INFORMATION_CLASS enumeration type represents the type of information to set for a registry key.
old-location: kernel\key_set_information_class.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["KEY_SET_INFORMATION_CLASS enumeration"]
ms.keywords: KEY_SET_INFORMATION_CLASS, KEY_SET_INFORMATION_CLASS enumeration [Kernel-Mode Driver Architecture], KeyControlFlagsInformation, KeySetDebugInformation, KeySetHandleTagsInformation, KeySetVirtualizationInformation, KeyWow64FlagsInformation, KeyWriteTimeInformation, MaxKeySetInfoClass, _KEY_SET_INFORMATION_CLASS, kernel.key_set_information_class, sysenum_b2121228-e221-424c-8e84-cd213d91716b.xml, wdm/KEY_SET_INFORMATION_CLASS, wdm/KeyControlFlagsInformation, wdm/KeySetDebugInformation, wdm/KeySetHandleTagsInformation, wdm/KeySetVirtualizationInformation, wdm/KeyWow64FlagsInformation, wdm/KeyWriteTimeInformation, wdm/MaxKeySetInfoClass
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows XP.
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
req.typenames: KEY_SET_INFORMATION_CLASS
f1_keywords:
 - _KEY_SET_INFORMATION_CLASS
 - wdm/_KEY_SET_INFORMATION_CLASS
 - KEY_SET_INFORMATION_CLASS
 - wdm/KEY_SET_INFORMATION_CLASS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - _KEY_SET_INFORMATION_CLASS
 - KEY_SET_INFORMATION_CLASS
---

# _KEY_SET_INFORMATION_CLASS enumeration


## -description

The <b>KEY_SET_INFORMATION_CLASS</b> enumeration type represents the type of information to set for a registry key.

## -enum-fields

### -field KeyWriteTimeInformation

Indicates that a <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_key_write_time_information">KEY_WRITE_TIME_INFORMATION</a> structure is supplied.

### -field KeyWow64FlagsInformation

Reserved for system use.

### -field KeyControlFlagsInformation

Reserved for system use.

### -field KeySetVirtualizationInformation

Reserved for system use.

### -field KeySetDebugInformation

Reserved for system use.

### -field KeySetHandleTagsInformation

Reserved for system use.

### -field KeySetLayerInformation

### -field MaxKeySetInfoClass

This member constant is always the maximum value in the enumeration.

## -remarks

A <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a> routine can receive a pointer to a <b>KEY_SET_INFORMATION_CLASS</b> structure as an input parameter.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_key_write_time_information">KEY_WRITE_TIME_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-ex_callback_function">RegistryCallback</a>

