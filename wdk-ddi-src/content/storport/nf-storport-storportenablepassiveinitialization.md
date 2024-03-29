---
UID: NF:storport.StorPortEnablePassiveInitialization
title: StorPortEnablePassiveInitialization function (storport.h)
description: The StorPortEnablePassiveInitialization routine enables the miniport's HwStorPassiveInitializeRoutine callback routine to execute at PASSIVE_LEVEL during miniport initialization.
old-location: storage\storportenablepassiveinitialization.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["StorPortEnablePassiveInitialization function"]
ms.keywords: StorPortEnablePassiveInitialization, StorPortEnablePassiveInitialization routine [Storage Devices], storage.storportenablepassiveinitialization, storport/StorPortEnablePassiveInitialization, storprt_faea18e4-c684-4010-aca4-177132c011c5.xml
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: StorPortEnablePassive, StorPortPassiveFromHwInit
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: DIRQL
targetos: Windows
req.typenames: 
f1_keywords:
 - StorPortEnablePassiveInitialization
 - storport/StorPortEnablePassiveInitialization
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - StorPortEnablePassiveInitialization
---

# StorPortEnablePassiveInitialization function


## -description

The <b>StorPortEnablePassiveInitialization</b> routine enables  the miniport's <a href="/windows-hardware/drivers/ddi/storport/nc-storport-hw_passive_initialize_routine">HwStorPassiveInitializeRoutine</a> callback routine to execute at PASSIVE_LEVEL during miniport initialization.

## -parameters

### -param DeviceExtension [in]


Pointer to the per-adapter device extension.

### -param HwPassiveInitializeRoutine [in]


Pointer to a callback routine that the port driver calls at PASSIVE_LEVEL to initialize the DPCs that the miniport driver will use. For a description of this callback routine, see [HwStorPassiveInitializeRoutine](./nc-storport-hw_passive_initialize_routine.md).

## -returns

The <b>StorPortEnablePassiveInitialization</b> routine returns <b>TRUE</b> if the operating system supports DPCs, and <b>FALSE</b> if not.

## -remarks

A miniport must call the <b>StorPortEnablePassiveInitialization</b> routine only from within <a href="/windows-hardware/drivers/ddi/storport/nc-storport-hw_initialize">HwStorInitialize</a>. Otherwise, <b>StorPortEnablePassiveInitialization</b> will return <b>FALSE</b> and the <a href="/windows-hardware/drivers/ddi/storport/nc-storport-hw_passive_initialize_routine">HwStorPassiveInitializeRoutine</a> routine will not execute.

This routine is implemented using inline function definitions, so that miniport drivers that use this routine will not have to link to libraries that are dependent on the version of the operating system. Miniport drivers can use this routine without sacrificing backward compatibility with versions of the operating system that do not support DPCs in storage miniport drivers.

## -see-also

<a href="/windows-hardware/drivers/ddi/storport/nc-storport-hw_passive_initialize_routine">HwStorPassiveInitializeRoutine</a>
