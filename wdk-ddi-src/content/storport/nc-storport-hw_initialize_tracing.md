---
UID: NC:storport.HW_INITIALIZE_TRACING
title: HW_INITIALIZE_TRACING (storport.h)
description: The HwStorInitializeTracing callback routine allows the Storport virtual miniport driver to set up tracing and any related resources.
old-location: storage\hwstorinitializetracing.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["HW_INITIALIZE_TRACING callback function"]
ms.keywords: HW_INITIALIZE_TRACING, HwStorInitializeTracing, HwStorInitializeTracing routine [Storage Devices], storage.hwstorinitializetracing, storport/HwStorInitializeTracing, storvmini_0c53c6e6-7c5c-4400-b923-c03a7756614f.xml
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
 - HW_INITIALIZE_TRACING
 - storport/HW_INITIALIZE_TRACING
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Storport.h
api_name:
 - HW_INITIALIZE_TRACING
---

# HW_INITIALIZE_TRACING callback function

## -description

The **HwStorInitializeTracing** callback routine allows the Storport virtual miniport driver to set up tracing and any related resources.

## -parameters

### -param Arg1

The first parameter that is passed to [**StorPortInitialize**](nf-storport-storportinitialize.md).

### -param Arg2

The second parameter that is passed to [**StorPortInitialize**](nf-storport-storportinitialize.md).

## -remarks

The name **HwStorInitializeTracing** is placeholder text for the actual routine name. The actual prototype of this routine is defined in Storport.h as follows:

``` c
typedef
VOID
HW_INITIALIZE_TRACING (
  _In_ PVOID  Arg1,
  _In_ PVOID  Arg2
  );
```

The port driver calls the Storport virtual miniport's **HwStorInitializeTracing** at PASSIVE_LEVEL.

### Examples

To define an **HwStorInitializeTracing** callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps [Code Analysis for Drivers](/windows-hardware/drivers/devtest/code-analysis-for-drivers), [Static Driver Verifier](/windows-hardware/drivers/devtest/static-driver-verifier) (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

 For example, to define a **HwStorInitializeTracing** callback routine that is named **MyHwInitializeTracing**, use the **HW_INITIALIZE_TRACING** type as shown in this code example:

``` c
HW_INITIALIZE_TRACING MyHwInitializeTracing;
```

Then, implement your callback routine as follows:

``` c
_Use_decl_annotations_
VOID
MyHwInitializeTracing (
  _In_ PVOID  Arg1,
  _In_ PVOID  Arg2
  );
  {
      ...
  }
```

The **HW_INITIALIZE_TRACING** function type is defined in the Storport.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the **HW_INITIALIZE_TRACING** function type in the header file are used. For more information about the requirements for function declarations, see [Declaring Functions Using Function Role Types for Storport Drivers](/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-storport-drivers). For information about _Use_decl_annotations_, see [Annotating Function Behavior](/visualstudio/code-quality/annotating-function-behavior).
