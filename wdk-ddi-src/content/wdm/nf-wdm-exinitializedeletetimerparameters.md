---
UID: NF:wdm.ExInitializeDeleteTimerParameters
title: ExInitializeDeleteTimerParameters function (wdm.h)
description: The ExInitializeDeleteTimerParameters routine initializes an EXT_DELETE_PARAMETERS structure.
old-location: kernel\exinitializedeletetimerparameters.htm
tech.root: kernel
ms.assetid: 2AD23AE1-05FF-44AF-807F-1ABD9D0D24DA
ms.date: 04/30/2018
keywords: ["ExInitializeDeleteTimerParameters function"]
ms.keywords: ExInitializeDeleteTimerParameters, ExInitializeDeleteTimerParameters routine [Kernel-Mode Driver Architecture], kernel.exinitializedeletetimerparameters, wdm/ExInitializeDeleteTimerParameters
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
 - ExInitializeDeleteTimerParameters
 - wdm/ExInitializeDeleteTimerParameters
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - ExInitializeDeleteTimerParameters
---

# ExInitializeDeleteTimerParameters function


## -description

The <b>ExInitializeDeleteTimerParameters</b> routine initializes an <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_ext_delete_parameters">EXT_DELETE_PARAMETERS</a> structure.

## -parameters

### -param Parameters

A pointer to the <b>EXT_DELETE_PARAMETERS</b> structure that is to be initialized.

## -remarks

Your driver must call <b>ExInitializeDeleteTimerParameters</b> to initialize an <b>EXT_DELETE_PARAMETERS</b> structure before the driver passes this structure to the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exdeletetimer">ExDeleteTimer</a> routine. For more information about the member values that <b>ExInitializeDeleteTimerParameters</b> writes to the members of this structure, see <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_ext_delete_parameters">EXT_DELETE_PARAMETERS</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_ext_delete_parameters">EXT_DELETE_PARAMETERS</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exdeletetimer">ExDeleteTimer</a>