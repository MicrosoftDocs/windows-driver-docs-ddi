---
UID: NF:aux_klib.AuxKlibGetBugCheckData
title: AuxKlibGetBugCheckData function (aux_klib.h)
description: The AuxKlibGetBugCheckData routine retrieves information about a bug check that has just occurred.
old-location: kernel\auxklibgetbugcheckdata.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["AuxKlibGetBugCheckData function"]
ms.keywords: AuxKlibGetBugCheckData, AuxKlibGetBugCheckData routine [Kernel-Mode Driver Architecture], aux_klib/AuxKlibGetBugCheckData, aux_klib_3cb977df-feb6-4b52-afa1-b5e3038fc287.xml, kernel.auxklibgetbugcheckdata
req.header: aux_klib.h
req.include-header: Aux_klib.h
req.target-type: Universal
req.target-min-winverclnt: Supported starting with Windows 2000.
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
req.lib: Aux_Klib.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - AuxKlibGetBugCheckData
 - aux_klib/AuxKlibGetBugCheckData
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Aux_Klib.lib
 - Aux_Klib.dll
api_name:
 - AuxKlibGetBugCheckData
---

# AuxKlibGetBugCheckData function


## -description

The <b>AuxKlibGetBugCheckData</b> routine retrieves information about a bug check that has just occurred.

## -parameters

### -param BugCheckData [out]


A pointer to a <a href="/windows-hardware/drivers/ddi/aux_klib/ns-aux_klib-_kbugcheck_data">KBUGCHECK_DATA</a> structure that contains information about the bug check. The <i>BugCheckData</i> size of this structure should be set equal to the size, in bytes, of the <b>KBUGCHECK_DATA</b> structure.

## -returns

<b>AuxKlibGetBugCheckData</b> returns STATUS_SUCCESS if the operation succeeds. The routine returns STATUS_INFO_LENGTH_MISMATCH if the <b>KBUGCHECK_DATA</b> structure's size is incorrect.

## -remarks

The <b>AuxKlibGetBugCheckData</b> routine can be called only from a <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-kbugcheck_callback_routine">BugCheckCallback</a> routine.

Drivers must call <a href="/windows-hardware/drivers/ddi/aux_klib/nf-aux_klib-auxklibinitialize">AuxKlibInitialize</a> before calling <b>AuxKlibGetBugCheckData</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/aux_klib/nf-aux_klib-auxklibinitialize">AuxKlibInitialize</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-kbugcheck_callback_routine">BugCheckCallback</a>



<a href="/windows-hardware/drivers/ddi/aux_klib/ns-aux_klib-_kbugcheck_data">KBUGCHECK_DATA</a>
