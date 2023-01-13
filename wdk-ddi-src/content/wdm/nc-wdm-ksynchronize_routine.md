---
UID: NC:wdm.KSYNCHRONIZE_ROUTINE
title: KSYNCHRONIZE_ROUTINE (wdm.h)
description: The SynchCritSection routine is used to access hardware resources or driver data that are shared with a driver's InterruptService routine.
tech.root: kernel
ms.date: 01/10/2023
keywords: ["KSYNCHRONIZE_ROUTINE callback function"]
ms.keywords: DrvrRtns_ead80ba6-d012-4140-923c-683d877d5b60.xml, KSYNCHRONIZE_ROUTINE, SynchCritSection, SynchCritSection routine [Kernel-Mode Driver Architecture], kernel.synchcritsection, wdm/SynchCritSection
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
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
req.irql: Called at DIRQL (see Remarks section).
targetos: Windows
req.typenames: 
f1_keywords:
 - KSYNCHRONIZE_ROUTINE
 - wdm/KSYNCHRONIZE_ROUTINE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - KSYNCHRONIZE_ROUTINE
---

## -description

The *SynchCritSection* routine is used to access hardware resources or driver data that are shared with a driver's [InterruptService](/windows-hardware/drivers/ddi/wdm/nc-wdm-kservice_routine) routine.

## -parameters

### -param SynchronizeContext [in]

Caller-supplied context information, specified by the driver's call to [KeSynchronizeExecution](/windows-hardware/drivers/ddi/wdm/nf-wdm-kesynchronizeexecution).

## -returns

If the routine's operation succeeds, the routine should return **TRUE**; otherwise, it should return **FALSE**. (Success and failure of this routine are driver-defined.) The specified return value becomes the return value for **KeSynchronizeExecution**.

## -remarks

Drivers must use *SynchCritSection* routines to access hardware resources or driver data that can also be accessed by an *InterruptService* routine (ISR).

The system calls a driver's *SynchCritSection* routine when the driver calls [KeSynchronizeExecution](/windows-hardware/drivers/ddi/wdm/nf-wdm-kesynchronizeexecution). When a driver calls **KeSynchronizeExecution**, it specifies the address of a *SynchCritSection* routine, context information for the routine, and an interrupt object pointer. The **KeSynchronizeExecution** routine acquires the interrupt object's spin lock, then calls the *SynchCritSection* routine.

A driver's *SynchCritSection* routine executes at the same IRQL as the ISR with which it is associated. Specifically, it executes at some system-assigned [DIRQL](/windows-hardware/drivers/), as specified by the *SynchronizeIrql* parameter to [IoConnectInterrupt](/windows-hardware/drivers/ddi/wdm/nf-wdm-ioconnectinterrupt). (Other devices, with higher DIRQL values, can interrupt a *SynchCritSection* routine.)

### Examples

To define a *SynchCritSection* callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps [Code Analysis for Drivers](/windows-hardware/drivers/devtest/code-analysis-for-drivers), [Static Driver Verifier](/windows-hardware/drivers/devtest/static-driver-verifier) (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a *SynchCritSection* callback routine that is named `MySynchCritSection`, use the KSYNCHRONIZE_ROUTINE type as shown in this code example:

```cpp
KSYNCHRONIZE_ROUTINE MySynchCritSection;
```

Then, implement your callback routine as follows:

```cpp
_Use_decl_annotations_
BOOLEAN
  MySynchCritSection(
    PVOID  SynchronizeContext
    )
  {
      // Function body
  }
```

The KSYNCHRONIZE_ROUTINE function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the `_Use_decl_annotations_` annotation to your function definition. The `_Use_decl_annotations_` annotation ensures that the annotations that are applied to the KSYNCHRONIZE_ROUTINE function type in the header file are used. For more information about the requirements for function declarations, see [Declaring Functions by Using Function Role Types for WDM Drivers](/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers). For information about `_Use_decl_annotations_`, see [Annotating Function Behavior](/visualstudio/code-quality/annotating-function-behavior).
