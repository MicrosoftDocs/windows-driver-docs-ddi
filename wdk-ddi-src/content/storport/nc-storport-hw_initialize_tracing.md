---
UID: NC:storport.HW_INITIALIZE_TRACING
title: HW_INITIALIZE_TRACING
author: windows-driver-content
description: The HwStorInitializeTracing callback routine allows the Storport virtual miniport driver to set up tracing and any related resources.
old-location: storage\hwstorinitializetracing.htm
old-project: storage
ms.assetid: e0d4ea58-415b-4ea4-9001-8a23ab44a1bf
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _STORAGE_DEVICE_UNIQUE_IDENTIFIER, *PSTORAGE_DEVICE_UNIQUE_IDENTIFIER, STORAGE_DEVICE_UNIQUE_IDENTIFIER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HwStorInitializeTracing
req.alt-loc: Storport.h
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
req.typenames: *PSTORAGE_DEVICE_UNIQUE_IDENTIFIER, STORAGE_DEVICE_UNIQUE_IDENTIFIER
req.product: Windows 10 or later.
---

# HW_INITIALIZE_TRACING callback



## -description
The <b>HwStorInitializeTracing</b> callback routine allows the Storport virtual miniport driver to set up tracing and any related resources.



## -prototype

````
HW_INITIALIZE_TRACING HwStorInitializeTracing;

VOID HwStorInitializeTracing(
   IN PVOID Arg1,
   IN PVOID Arg2
)
{ ... }
````


## -parameters

### -param Arg1 

The first parameter that is passed to <a href="..\storport\nf-storport-storportinitialize.md">StorPortInitialize</a>.


### -param Arg2 

The second parameter that is passed to <a href="..\storport\nf-storport-storportinitialize.md">StorPortInitialize</a>.


## -returns
None


## -remarks
The name <b>HwStorInitializeTracing</b> is placeholder text for the actual routine name. The actual prototype of this routine is defined in Storport.h as follows:

The port driver calls the Storport virtual miniport's <b>HwStorInitializeTracing</b> at PASSIVE_LEVEL.

To define an <b>HwStorInitializeTracing</b> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

 For example, to define a <b>HwStorInitializeTracing</b> callback routine that is named <i>MyHwInitializeTracing</i>, use the <b>HW_INITIALIZE_TRACING</b> type as shown in this code example:

Then, implement your callback routine as follows:

The <b>HW_INITIALIZE_TRACING</b> function type is defined in the Storport.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>HW_INITIALIZE_TRACING</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/40BD11CD-A559-4F90-BF39-4ED2FB800392">Declaring Functions Using Function Role Types for Storport Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-us/library/jj159529.aspx">Annotating Function Behavior</a>.</p>