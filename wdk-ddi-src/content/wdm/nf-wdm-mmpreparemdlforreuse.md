---
UID: NF:wdm.MmPrepareMdlForReuse
tech.root: 
title: MmPrepareMdlForReuse
ms.date: 07/16/2021
targetos: Windows
description: "Learn more about: MmPrepareMdlForReuse"
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
req.irql: <= DISPATCH_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 2000
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - MmPrepareMdlForReuse
f1_keywords:
 - MmPrepareMdlForReuse
 - wdm/MmPrepareMdlForReuse
dev_langs:
 - c++
---

## -description

The **MmPrepareMdlForReuse** macro releases the resources that are associated with a partial MDL so that the MDL can be reused.

## -parameters

### -param MDL

[in]
A pointer to a partial MDL that is to be prepared for reuse.

## -remarks

This macro is used by drivers that repeatedly use the same allocated MDL for the _TargetMdl_ parameter in calls to the [**IoBuildPartialMdl**](/windows-hardware/drivers/ddi/wdm/nf-wdm-iobuildpartialmdl) routine. If, in a call to **MmPrepareMdlForReuse**, the specified partial MDL has an associated mapping to system address space, **MmPrepareMdlForReuse** releases the mapping so that the MDL can be reused.

**MmPrepareMdlForReuse** accepts only partial MDLs that are built by **IoBuildPartialMdl**. If **MmPrepareMdlForReuse** receives an MDL that is mapped to the system address space but was not built by **IoBuildPartialMdl**, **MmPrepareMdlForReuse** does not release the mapping.

For more information about partial MDLs, see [Using MDLs](/windows-hardware/drivers/kernel/using-mdls).
