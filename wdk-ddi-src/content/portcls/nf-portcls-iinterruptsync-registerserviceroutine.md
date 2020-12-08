---
UID: NF:portcls.IInterruptSync.RegisterServiceRoutine
title: IInterruptSync::RegisterServiceRoutine (portcls.h)
description: The RegisterServiceRoutine method registers an interrupt service routine (ISR) that is to be called when an interrupt occurs.
old-location: audio\iinterruptsync_registerserviceroutine.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["IInterruptSync::RegisterServiceRoutine"]
ms.keywords: IInterruptSync interface [Audio Devices],RegisterServiceRoutine method, IInterruptSync.RegisterServiceRoutine, IInterruptSync::RegisterServiceRoutine, RegisterServiceRoutine, RegisterServiceRoutine method [Audio Devices], RegisterServiceRoutine method [Audio Devices],IInterruptSync interface, audio.iinterruptsync_registerserviceroutine, audmp-routines_92919bdc-00aa-4911-ac3c-58a0807c7212.xml, portcls/IInterruptSync::RegisterServiceRoutine
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IInterruptSync::RegisterServiceRoutine
 - portcls/IInterruptSync::RegisterServiceRoutine
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IInterruptSync.RegisterServiceRoutine
---

# IInterruptSync::RegisterServiceRoutine


## -description

The <code>RegisterServiceRoutine</code> method registers an interrupt service routine (ISR) that is to be called when an interrupt occurs.

## -parameters

### -param Routine 

[in]
Pointer to the routine that is to be called. This parameter is a function pointer of type PINTERRUPTSYNCROUTINE (see <a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iinterruptsync">IInterruptSync</a>).

### -param DynamicContext 

[in]
Specifies a context value that is passed to the routine when it is called.

### -param First 

[in]
Specifies whether the routine is added at the head or tail of the list of ISRs. If <b>TRUE</b>, the routine is added at the head of the list. If <b>FALSE</b>, it is added at the tail.

## -returns

<code>RegisterServiceRoutine</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.

## -remarks

This method adds the specified routine to the synchronization object's list of ISRs. When an interrupt occurs, the routine at the head of the list is called first, and the routine at the tail is called last.
