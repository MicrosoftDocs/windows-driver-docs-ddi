---
UID: NC:storport.HW_CLEANUP_TRACING
title: HW_CLEANUP_TRACING (storport.h)
description: The HwStorCleanupTracing callback routine allows the Storport virtual miniport driver to stop tracing and to free any related resources.
old-location: storage\hwstorcleanuptracing.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["HW_CLEANUP_TRACING callback function"]
ms.keywords: HW_CLEANUP_TRACING, HwStorCleanupTracing, HwStorCleanupTracing routine [Storage Devices], storage.hwstorcleanuptracing, storport/HwStorCleanupTracing, storvmini_7a5c9359-04e5-4ad4-b638-14cce4087df2.xml
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
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - HW_CLEANUP_TRACING
 - storport/HW_CLEANUP_TRACING
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Storport.h
api_name:
 - HW_CLEANUP_TRACING
---

# HW_CLEANUP_TRACING callback function

## -description

The **HwStorCleanupTracing** callback routine allows the Storport virtual miniport driver to stop tracing and to free any related resources.

## -parameters

### -param Arg1

A pointer to the driver object.

## -remarks

The name **HwStorCleanupTracing** is placeholder text for the actual routine name. The actual prototype of this routine is defined in Storport.h as follows:

``` c
typedef
VOID
HW_CLEANUP_TRACING (
  IN PVOID  Arg1
  );
```

The port driver calls the Storport virtual miniport's **HwStorCleanupTracing** at PASSIVE_LEVEL.

### Examples

To define an **HwStorCleanupTracing** callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps [Code Analysis for Drivers](/windows-hardware/drivers/devtest/code-analysis-for-drivers), [Static Driver Verifier](/windows-hardware/drivers/devtest/static-driver-verifier) (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

 For example, to define a **HwStorCleanupTracing** callback routine that is named **MyHwCleanupTracing**, use the **HW_CLEANUP_TRACING** type as shown in this code example:

``` c
HW_CLEANUP_TRACING MyHwCleanupTracing;
```

Then, implement your callback routine as follows:

``` c
_Use_decl_annotations_
VOID
MyHwCleanupTracing (
  _In_ PVOID  Arg1
  );
  {
      ...
  }
```

The **HW_CLEANUP_TRACING** function type is defined in the Storport.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the **HW_CLEANUP_TRACING** function type in the header file are used. For more information about the requirements for function declarations, see [Declaring Functions Using Function Role Types for Storport Drivers](/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-storport-drivers). For information about _Use_decl_annotations_, see [Annotating Function Behavior](/visualstudio/code-quality/annotating-function-behavior).
