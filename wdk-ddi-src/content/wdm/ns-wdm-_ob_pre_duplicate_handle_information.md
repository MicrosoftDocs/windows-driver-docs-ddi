---
UID: NS:wdm._OB_PRE_DUPLICATE_HANDLE_INFORMATION
title: _OB_PRE_DUPLICATE_HANDLE_INFORMATION (wdm.h)
description: The OB_PRE_DUPLICATE_HANDLE_INFORMATION structure provides information to an ObjectPreCallback routine about a thread or process handle that is being duplicated.
old-location: kernel\ob_pre_duplicate_handle_information.htm
tech.root: kernel
ms.assetid: f2798729-98a2-44b6-94a6-180bb4db96cb
ms.date: 04/30/2018
keywords: ["OB_PRE_DUPLICATE_HANDLE_INFORMATION structure"]
ms.keywords: "*POB_PRE_DUPLICATE_HANDLE_INFORMATION, OB_PRE_DUPLICATE_HANDLE_INFORMATION, OB_PRE_DUPLICATE_HANDLE_INFORMATION structure [Kernel-Mode Driver Architecture], POB_PRE_DUPLICATE_HANDLE_INFORMATION, POB_PRE_DUPLICATE_HANDLE_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _OB_PRE_DUPLICATE_HANDLE_INFORMATION, kernel.ob_pre_duplicate_handle_information, kstruct_c_5511a4ac-ea2e-412f-8514-021853d5abfd.xml, wdm/OB_PRE_DUPLICATE_HANDLE_INFORMATION, wdm/POB_PRE_DUPLICATE_HANDLE_INFORMATION"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Server 2008 and later versions of the Windows operating system.
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
req.typenames: OB_PRE_DUPLICATE_HANDLE_INFORMATION, *POB_PRE_DUPLICATE_HANDLE_INFORMATION
f1_keywords:
 - _OB_PRE_DUPLICATE_HANDLE_INFORMATION
 - wdm/_OB_PRE_DUPLICATE_HANDLE_INFORMATION
 - POB_PRE_DUPLICATE_HANDLE_INFORMATION
 - wdm/POB_PRE_DUPLICATE_HANDLE_INFORMATION
 - OB_PRE_DUPLICATE_HANDLE_INFORMATION
 - wdm/OB_PRE_DUPLICATE_HANDLE_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - OB_PRE_DUPLICATE_HANDLE_INFORMATION
---

# _OB_PRE_DUPLICATE_HANDLE_INFORMATION structure


## -description

The <b>OB_PRE_DUPLICATE_HANDLE_INFORMATION</b> structure provides information to an <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pob_pre_operation_callback">ObjectPreCallback</a> routine about a thread or process handle that is being duplicated.

## -struct-fields

### -field DesiredAccess

An <a href="/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a> value that specifies the access rights to grant for the handle. By default, this member equals <i>OriginalDesiredAccess</i>, but the <i>ObjectPreCallback</i> routine can modify this value to restrict the access that is granted. For a description of the access rights that drivers can use, see <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_ob_pre_create_handle_information">OB_PRE_CREATE_HANDLE_INFORMATION</a>.

### -field OriginalDesiredAccess

An ACCESS_MASK value that specifies the original access that was requested for the handle.

### -field SourceProcess

A pointer to the process object for the process that is the source of the handle.

### -field TargetProcess

A pointer to the process object for the process that receives the duplicated handle.

## -remarks

You can never add access rights beyond what is specified in the <b>DesiredAccess</b> member. If the access right is listed as a modifiable flag, the access right can be removed.

## -see-also

<a href="/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pob_pre_operation_callback">ObjectPreCallback</a>