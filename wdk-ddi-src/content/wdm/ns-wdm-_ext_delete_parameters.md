---
UID: NS:wdm._EXT_DELETE_PARAMETERS
title: _EXT_DELETE_PARAMETERS (wdm.h)
description: The EXT_DELETE_PARAMETERS structure contains an extended set of parameters for the ExDeleteTimer routine.
old-location: kernel\ext_delete_parameters.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["EXT_DELETE_PARAMETERS structure"]
ms.keywords: "*PEXT_DELETE_PARAMETERS, EXT_DELETE_PARAMETERS, EXT_DELETE_PARAMETERS structure [Kernel-Mode Driver Architecture], PEXT_DELETE_PARAMETERS, PEXT_DELETE_PARAMETERS structure pointer [Kernel-Mode Driver Architecture], _EXT_DELETE_PARAMETERS, kernel.ext_delete_parameters, wdm/EXT_DELETE_PARAMETERS, wdm/PEXT_DELETE_PARAMETERS"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.1.
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
req.typenames: EXT_DELETE_PARAMETERS, *PEXT_DELETE_PARAMETERS
f1_keywords:
 - _EXT_DELETE_PARAMETERS
 - wdm/_EXT_DELETE_PARAMETERS
 - PEXT_DELETE_PARAMETERS
 - wdm/PEXT_DELETE_PARAMETERS
 - EXT_DELETE_PARAMETERS
 - wdm/EXT_DELETE_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - EXT_DELETE_PARAMETERS
---

# _EXT_DELETE_PARAMETERS structure


## -description

The <b>EXT_DELETE_PARAMETERS</b> structure contains an extended set of parameters for the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exdeletetimer">ExDeleteTimer</a> routine.

## -struct-fields

### -field Version

The version number of this <b>EXT_DELETE_PARAMETERS</b> structure. The <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializedeletetimerparameters">ExInitializeDeleteTimerParameters</a> routine sets this member to the correct version number.

### -field Reserved

Set to zero. The <b>ExInitializeDeleteTimerParameters</b> routine sets this member to zero.

### -field DeleteCallback

A pointer to a driver-implemented <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-ext_delete_callback">ExTimerDeleteCallback</a> callback routine. The operating system calls this routine when the timer is deleted. This parameter is optional and can be <b>NULL</b> if no timer-deletion callback routine is needed.

The <b>ExInitializeDeleteTimerParameters</b> routine sets this member to <b>NULL</b>. For more information, see Remarks.

### -field DeleteContext

A context value for the timer-deletion callback routine. The operating system passes this value as a parameter to the timer-deletion callback routine, if one is specified. This parameter is typically a pointer to a caller-defined structure that contains context information used by the callback routine. This parameter is optional and can be set to <b>NULL</b> if no context information is needed. 

The <b>ExInitializeDeleteTimerParameters</b> routine sets this member to <b>NULL</b>.

## -remarks

The <i>Parameters</i> parameter of the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exdeletetimer">ExDeleteTimer</a> routine is a pointer to an <b>EXT_DELETE_PARAMETERS</b> structure. Before passing an <b>EXT_DELETE_PARAMETERS</b> structure to this routine, call the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializedeletetimerparameters">ExInitializeDeleteTimerParameters</a> routine to initialize the structure.

Your driver can use an <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-ext_delete_callback">ExTimerDeleteCallback</a> callback routine to free any storage or other system resources that the driver might have previously allocated to use with the timer object that is being deleted. For example, the driver's context value might point to a caller-allocated structure that needs to be freed if the timer object is to be deleted. The operating system calls the <i>ExTimerDeleteCallback</i> routine only after the timer object has been disabled to prevent further timer operations and any pending timer operation on the timer object is canceled or completed.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exdeletetimer">ExDeleteTimer</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializedeletetimerparameters">ExInitializeDeleteTimerParameters</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-ext_delete_callback">ExTimerDeleteCallback</a>
