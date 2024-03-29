---
UID: NF:wdm.ExInitializeSetTimerParameters
title: ExInitializeSetTimerParameters function (wdm.h)
description: The ExInitializeSetTimerParameters routine initializes an EXT_SET_PARAMETERS structure.
old-location: kernel\exinitializesettimerparameters.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["ExInitializeSetTimerParameters function"]
ms.keywords: ExInitializeSetTimerParameters, ExInitializeSetTimerParameters routine [Kernel-Mode Driver Architecture], kernel.exinitializesettimerparameters, wdm/ExInitializeSetTimerParameters
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8.1.
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
req.irql: Any level.
targetos: Windows
req.typenames: 
f1_keywords:
 - ExInitializeSetTimerParameters
 - wdm/ExInitializeSetTimerParameters
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - ExInitializeSetTimerParameters
---

# ExInitializeSetTimerParameters function


## -description

The <b>ExInitializeSetTimerParameters</b> routine initializes an <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_ext_set_parameters_v0">EXT_SET_PARAMETERS</a> structure.

## -parameters

### -param Parameters [out]


A pointer to the <b>EXT_SET_PARAMETER</b> structure that is to be initialized.

## -remarks

Your driver must call <b>ExInitializeSetTimerParameters</b> to initialize an <b>EXT_SET_PARAMETERS</b> structure before the driver passes this structure to the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exsettimer">ExSetTimer</a> routine. For more information about the member values that <b>ExInitializeSetTimerParameters</b> writes to the members of this structure, see <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_ext_set_parameters_v0">EXT_SET_PARAMETERS</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_ext_set_parameters_v0">EXT_SET_PARAMETERS</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exsettimer">ExSetTimer</a>
