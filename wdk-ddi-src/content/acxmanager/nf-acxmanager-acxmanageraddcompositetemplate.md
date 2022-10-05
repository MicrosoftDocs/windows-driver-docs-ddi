---
UID: NF:acxmanager.AcxManagerAddCompositeTemplate
tech.root: audio
title: AcxManagerAddCompositeTemplate
ms.date: 04/27/2022
targetos: Windows
description: The AcxManagerAddCompositeTemplate function adds the specified composite template to the specified ACXMANAGER.
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
 - AcxManagerAddCompositeTemplate
f1_keywords:
 - AcxManagerAddCompositeTemplate
 - acxmanager/AcxManagerAddCompositeTemplate
dev_langs:
 - c++
---

## -description

The **AcxManagerAddCompositeTemplate** function adds the specified composite template to the specified **ACXMANAGER**.

## -parameters

### -param Manager [in]

The **ACXMANAGER** to which the specified *Template* is added.

### -param Template [in]

The composite template to add to the specified *Manager*.

## -returns

The method returns **STATUS_SUCCESS** if the operation succeeds. Otherwise, this method might return an appropriate **[NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values)** error code.

## -remarks

A composite template tells the ACX manager how to build a composite endpoint. For example, build an audio endpoint using two or more ACXCIRCUIT objects.

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxmanager.h header](index.md)

