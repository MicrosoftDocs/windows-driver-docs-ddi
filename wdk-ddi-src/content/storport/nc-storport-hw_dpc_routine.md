---
UID: NC:storport.HW_DPC_ROUTINE
title: HW_DPC_ROUTINE (storport.h)
description: The HwStorDpcRoutine routine is a routine that is deferred for execution at DISPATCH IRQL by means of the deferred procedure call (DPC) mechanism.
old-location: storage\hwstordpcroutine.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["HW_DPC_ROUTINE callback function"]
ms.keywords: HW_DPC_ROUTINE, HwStorDpcRoutine, HwStorDpcRoutine routine [Storage Devices], storage.hwstordpcroutine, stormini_593e93b3-e078-48a4-b192-75cc161686bb.xml, storport/HwStorDpcRoutine
req.header: storport.h
req.include-header: Storport.h
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
req.irql: DISPATCH_LEVEL (See Remarks section.)
targetos: Windows
req.typenames: 
f1_keywords:
 - HW_DPC_ROUTINE
 - storport/HW_DPC_ROUTINE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Storport.h
api_name:
 - HW_DPC_ROUTINE
---

# HW_DPC_ROUTINE callback function

## -description

The **HwStorDpcRoutine** routine is a routine that is deferred for execution at DISPATCH IRQL by means of the deferred procedure call (DPC) mechanism.

## -parameters

### -param Dpc

A pointer to a Storport DPC  context.

### -param HwDeviceExtension

A pointer to the per-adapter device extension.

### -param SystemArgument1

A pointer to caller-supplied information.

### -param SystemArgument2

A pointer to caller-supplied information.

## -remarks

When a miniport driver calls [**StorPortInitializeDpc**](nf-storport-storportinitializedpc.md) to initialize a DPC it must load the **HwDpcRoutine** parameter of the **StorPortInitializeDpc** routine with a pointer to the **HwStorDpcRoutine** routine.

Any particular instance of a DPC routine is guaranteed to be synchronized with other instances of the DPC routine. A DPC routine can synchronize itself with the [**HwStorStartIo**](nc-storport-hw_startio.md) routine or with the [**HwStorInterrupt**](nc-storport-hw_interrupt.md) routine by acquiring the appropriate spin lock with a call to [**StorPortAcquireSpinLock**](nf-storport-storportacquirespinlock.md). For more information about the management of spin locks within DPC routines, see [**StorPortIssueDpc**](nf-storport-storportissuedpc.md).

The name **HwStorDpcRoutine** is just a placeholder. The actual prototype of this routine is defined in *storport.h* as follows:

``` c
typedef
BOOLEAN
HW_DPC_ROUTINE (
  _In_  PSTOR_DPC Dpc,
  _In_  PVOID HwDeviceExtension,
  _In_opt_  PVOID SystemArgument1,
  _In_opt_  PVOID SystemArgument2
  );
```

The port driver calls the **HwStorDpcRoutine** routine at DISPATCH IRQL.

### Examples

To define an **HwStorDpcRoutine** callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps [Code Analysis for Drivers](/windows-hardware/drivers/devtest/code-analysis-for-drivers), [Static Driver Verifier](/windows-hardware/drivers/devtest/static-driver-verifier) (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

 For example, to define a **HwStorDpcRoutine** callback routine that is named **MyHwDpcRoutine**, use the **HW_DPC_ROUTINE** type as shown in this code example:

``` c
HW_DPC_ROUTINE MyHwDpcRoutine;
```

Then, implement your callback routine as follows:

``` c
_Use_decl_annotations_
BOOLEAN
MyHwDpcRoutine (
  _In_  PSTOR_DPC Dpc,
  _In_  PVOID HwDeviceExtension,
  _In_opt_  PVOID SystemArgument1,
  _In_opt_  PVOID SystemArgument2
  );
  {
      ...
  }
```

The **HW_DPC_ROUTINE** function type is defined in the Storport.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the **HW_DPC_ROUTINE** function type in the header file are used. For more information about the requirements for function declarations, see [Declaring Functions Using Function Role Types for Storport Drivers](/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-storport-drivers). For information about _Use_decl_annotations_, see [Annotating Function Behavior](/visualstudio/code-quality/annotating-function-behavior).

## -see-also

When a miniport driver calls  to initialize a DPC it must load the **HwDpcRoutine** parameter of the **StorPortInitializeDpc** routine with a pointer to the **HwStorDpcRoutine** routine.

Any particular instance of a DPC routine is guaranteed to be synchronized with other instances of the DPC routine. A DPC routine can synchronize itself with the  routine or with the  routine by acquiring the appropriate spin lock with a call to . For more information about the management of spin locks within DPC routines, see .

[**HwStorInterrupt**](nc-storport-hw_interrupt.md)

[**HwStorStartIo**](nc-storport-hw_startio.md)

[**StorPortAcquireSpinLock**](nf-storport-storportacquirespinlock.md)

[**StorPortInitializeDpc**](nf-storport-storportinitializedpc.md)

[**StorPortIssueDpc**](nf-storport-storportissuedpc.md)
