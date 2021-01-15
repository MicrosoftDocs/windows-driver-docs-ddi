---
UID: NE:wdm._RESOURCEMANAGER_INFORMATION_CLASS
title: _RESOURCEMANAGER_INFORMATION_CLASS (wdm.h)
description: The RESOURCEMANAGER_INFORMATION_CLASS enumeration identifies the type of information that the ZwQueryInformationResourceManager routine can retrieve for a resource manager object.
old-location: kernel\resourcemanager_information_class.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["RESOURCEMANAGER_INFORMATION_CLASS enumeration"]
ms.keywords: RESOURCEMANAGER_INFORMATION_CLASS, RESOURCEMANAGER_INFORMATION_CLASS enumeration [Kernel-Mode Driver Architecture], ResourceManagerBasicInformation, ResourceManagerCompletionInformation, _RESOURCEMANAGER_INFORMATION_CLASS, kernel.resourcemanager_information_class, ktm_ref_72b34c92-3548-4148-94c2-49f4a66ad4bf.xml, wdm/RESOURCEMANAGER_INFORMATION_CLASS, wdm/ResourceManagerBasicInformation, wdm/ResourceManagerCompletionInformation
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later operating system versions.
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
req.typenames: RESOURCEMANAGER_INFORMATION_CLASS
f1_keywords:
 - _RESOURCEMANAGER_INFORMATION_CLASS
 - wdm/_RESOURCEMANAGER_INFORMATION_CLASS
 - RESOURCEMANAGER_INFORMATION_CLASS
 - wdm/RESOURCEMANAGER_INFORMATION_CLASS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - _RESOURCEMANAGER_INFORMATION_CLASS
 - RESOURCEMANAGER_INFORMATION_CLASS
---

# _RESOURCEMANAGER_INFORMATION_CLASS enumeration


## -description

The <b>RESOURCEMANAGER_INFORMATION_CLASS</b> enumeration identifies the type of information that the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntqueryinformationresourcemanager">ZwQueryInformationResourceManager</a> routine can retrieve for a <a href="/windows-hardware/drivers/kernel/resource-manager-objects">resource manager object</a>.

## -enum-fields

### -field ResourceManagerBasicInformation

Information about a resource manager object is stored in a <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_resourcemanager_basic_information">RESOURCEMANAGER_BASIC_INFORMATION</a> structure.

### -field ResourceManagerCompletionInformation

Information about a resource manager object is stored in a <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_resourcemanager_completion_information">RESOURCEMANAGER_COMPLETION_INFORMATION</a> structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_resourcemanager_basic_information">RESOURCEMANAGER_BASIC_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_resourcemanager_completion_information">RESOURCEMANAGER_COMPLETION_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntqueryinformationresourcemanager">ZwQueryInformationResourceManager</a>

