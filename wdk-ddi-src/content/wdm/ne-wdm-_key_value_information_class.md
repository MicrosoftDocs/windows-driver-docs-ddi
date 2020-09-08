---
UID: NE:wdm._KEY_VALUE_INFORMATION_CLASS
title: _KEY_VALUE_INFORMATION_CLASS (wdm.h)
description: The KEY_VALUE_INFORMATION_CLASS enumeration type specifies the type of information to supply about the value of a registry key.
old-location: kernel\key_value_information_class.htm
tech.root: kernel
ms.assetid: 99a34b06-3352-47a6-95bc-051a5dfdd82e
ms.date: 04/30/2018
keywords: ["KEY_VALUE_INFORMATION_CLASS enumeration"]
ms.keywords: KEY_VALUE_INFORMATION_CLASS, KEY_VALUE_INFORMATION_CLASS enumeration [Kernel-Mode Driver Architecture], KeyValueBasicInformation, KeyValueFullInformation, KeyValueFullInformationAlign64, KeyValuePartialInformation, KeyValuePartialInformationAlign64, MaxKeyValueInfoClass, _KEY_VALUE_INFORMATION_CLASS, kernel.key_value_information_class, sysenum_ee3730f5-18b6-45ff-bb9b-4ec2e71586fc.xml, wdm/KEY_VALUE_INFORMATION_CLASS, wdm/KeyValueBasicInformation, wdm/KeyValueFullInformation, wdm/KeyValueFullInformationAlign64, wdm/KeyValuePartialInformation, wdm/KeyValuePartialInformationAlign64, wdm/MaxKeyValueInfoClass
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
req.irql: 
targetos: Windows
req.typenames: KEY_VALUE_INFORMATION_CLASS
f1_keywords:
 - _KEY_VALUE_INFORMATION_CLASS
 - wdm/_KEY_VALUE_INFORMATION_CLASS
 - KEY_VALUE_INFORMATION_CLASS
 - wdm/KEY_VALUE_INFORMATION_CLASS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - KEY_VALUE_INFORMATION_CLASS
---

# _KEY_VALUE_INFORMATION_CLASS enumeration


## -description

The <b>KEY_VALUE_INFORMATION_CLASS</b> enumeration type specifies the type of information to supply about the value of a registry key.

## -enum-fields

### -field KeyValueBasicInformation

The information is stored as a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_key_value_basic_information">KEY_VALUE_BASIC_INFORMATION</a> structure.

### -field KeyValueFullInformation

The information is stored as a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_key_value_full_information">KEY_VALUE_FULL_INFORMATION</a> structure.

### -field KeyValuePartialInformation

The information is stored as a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_key_value_partial_information">KEY_VALUE_PARTIAL_INFORMATION</a> structure.

### -field KeyValueFullInformationAlign64

The information is stored as a <b>KEY_VALUE_FULL_INFORMATION</b> structure that is aligned to a 64-bit (that is, 8-byte) boundary in memory. If the caller-supplied buffer does not start on a 64-bit boundary, [**ZwQueryValueKey**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwqueryvaluekey) returns **STATUS_DATATYPE_MISALIGNMENT**.

### -field KeyValuePartialInformationAlign64

The information is stored as a <b>KEY_VALUE_PARTIAL_INFORMATION_ALIGN64</b> structure that is aligned to a 64-bit (that is, 8-byte) boundary in memory. If the caller-supplied buffer does not start on a 64-bit boundary, [**ZwQueryValueKey**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwqueryvaluekey) returns **STATUS_DATATYPE_MISALIGNMENT**.

### -field KeyValueLayerInformation

### -field MaxKeyValueInfoClass

The maximum value in this enumeration type.

## -remarks

Use the <b>KEY_VALUE_INFORMATION_CLASS</b> values to specify the type of data to be supplied by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwenumeratevaluekey">ZwEnumerateValueKey</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwqueryvaluekey">ZwQueryValueKey</a> routines.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_key_value_basic_information">KEY_VALUE_BASIC_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_key_value_full_information">KEY_VALUE_FULL_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_key_value_partial_information">KEY_VALUE_PARTIAL_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwenumeratevaluekey">ZwEnumerateValueKey</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-zwqueryvaluekey">ZwQueryValueKey</a>

