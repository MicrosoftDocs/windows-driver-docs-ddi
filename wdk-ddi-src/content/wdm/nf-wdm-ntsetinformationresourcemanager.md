---
UID: NF:wdm.NtSetInformationResourceManager
title: NtSetInformationResourceManager function (wdm.h)
description: The ZwSetInformationResourceManager routine is not used.
old-location: kernel\zwsetinformationresourcemanager.htm
tech.root: kernel
ms.assetid: 0a0d86c7-1d42-4312-a4f9-9b9ea092ebec
ms.date: 04/30/2018
keywords: ["NtSetInformationResourceManager function"]
ms.keywords: NtSetInformationResourceManager, ZwSetInformationResourceManager, function [Kernel-Mode Driver Architecture], kernel.zwsetinformationresourcemanager, ktm_ref_6b15a16a-ffed-4f3e-9ca3-370b85896dc2.xml, wdm/, wdm/NtSetInformationResourceManager
req.header: wdm.h
req.include-header: 
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
req.typenames: 
f1_keywords:
 - NtSetInformationResourceManager
 - wdm/NtSetInformationResourceManager
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - ZwSetInformationResourceManager
 - NtSetInformationResourceManager
---

# NtSetInformationResourceManager function


## -description

The <b>ZwSetInformationResourceManager</b> routine is not used.

## -parameters

### -param ResourceManagerHandle

Not used.

### -param ResourceManagerInformationClass

Not used.

### -param ResourceManagerInformation

Not used.

### -param ResourceManagerInformationLength

Not used.

## -returns

This function does not return a value.

## -remarks

<b>NtSetInformationResourceManager</b> and <b>ZwSetInformationResourceManager</b> are two versions of the same Windows Native System Services routine.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.

## -see-also

<a href="/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>