---
UID: NS:aux_klib._KBUGCHECK_DATA
title: _KBUGCHECK_DATA (aux_klib.h)
description: The KBUGCHECK_DATA structure contains bug check parameters.
old-location: kernel\kbugcheck_data.htm
tech.root: kernel
ms.assetid: 9fecf57b-e77a-458e-80ce-118eed2d48b4
ms.date: 04/30/2018
keywords: ["_KBUGCHECK_DATA structure"]
ms.keywords: "*PKBUGCHECK_DATA, KBUGCHECK_DATA, KBUGCHECK_DATA structure [Kernel-Mode Driver Architecture], PKBUGCHECK_DATA, PKBUGCHECK_DATA structure pointer [Kernel-Mode Driver Architecture], _KBUGCHECK_DATA, aux_klib/KBUGCHECK_DATA, aux_klib/PKBUGCHECK_DATA, aux_klib_ced3c2df-3d09-45d8-8ae8-049d2bc46160.xml, kernel.kbugcheck_data"
f1_keywords:
 - "aux_klib/KBUGCHECK_DATA"
req.header: aux_klib.h
req.include-header: Aux_klib.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- aux_klib.h
api_name:
- KBUGCHECK_DATA
product:
- Windows
targetos: Windows
req.typenames: KBUGCHECK_DATA, *PKBUGCHECK_DATA
---

# _KBUGCHECK_DATA structure


## -description


The <b>KBUGCHECK_DATA</b> structure contains bug check parameters.


## -struct-fields




### -field BugCheckDataSize

The size, in bytes, of the <b>KBUGCHECK_DATA</b> structure. Callers of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/aux_klib/nf-aux_klib-auxklibgetbugcheckdata">AuxKlibGetBugCheckData</a> must supply this value. 


### -field BugCheckCode

The bug check code. This value identifies that type of bug check that has occurred.


### -field Parameter1

Bug check parameter 1. For more information about this parameter, see specific <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/bug-check-code-reference2">bug check codes</a>. 


### -field Parameter2

Bug check parameter 2. For more information about this parameter, see specific <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/bug-check-code-reference2">bug check codes</a>. 


### -field Parameter3

Bug check parameter 3. For more information about this parameter, see specific <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/bug-check-code-reference2">bug check codes</a>. 


### -field Parameter4

Bug check parameter 4. For more information about this parameter, see specific <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/bug-check-code-reference2">bug check codes</a>. 


## -remarks



The <b>KBUGCHECK_DATA</b> structure is used as a parameter to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/aux_klib/nf-aux_klib-auxklibgetbugcheckdata">AuxKlibGetBugCheckData</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/aux_klib/nf-aux_klib-auxklibgetbugcheckdata">AuxKlibGetBugCheckData</a>
 

 

