---
UID: NF:acxmanager.AcxManagerRemoveCompositeTemplate
tech.root: audio
title: AcxManagerRemoveCompositeTemplate
ms.date: 04/27/2022
targetos: Windows
description: The AcxManagerRemoveCompositeTemplate function removes the specified composite template from the specified ACXMANAGER.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxmanager.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - acxmanager.h
api_name:
 - AcxManagerRemoveCompositeTemplate
f1_keywords:
 - AcxManagerRemoveCompositeTemplate
 - acxmanager/AcxManagerRemoveCompositeTemplate
dev_langs:
 - c++
---

## -description

The **AcxManagerRemoveCompositeTemplate** function removes the specified composite template from the specified **ACXMANAGER**.

## -parameters

### -param Manager [in]

The **ACXMANAGER** from which the specified *Template* is removed.

### -param Template [in]

The composite template to remove from the specified *Manager*.

## -returns

The method returns **STATUS_SUCCESS** if the operation succeeds. Otherwise, this method might return an appropriate **[NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values)** error code.

## -remarks

When a composite template is removed, all endpoints associated with that composite template are also stopped and removed.

### ACX requirements

| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum ACX version** | 1.0 |

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxmanager.h header](index.md)

