---
UID: NE:dbgmodel.KnownCompiler
tech.root: debugger
title: KnownCompiler enumeration (dbgmodel.h)
ms.date:  10/31/2024
targetos: Windows
description: The KnownCompiler enumeration identifies a well-known set of compilers.  
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: dbgmodel.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: false
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dbgmodel.h
api_name:
 - KnownCompiler
f1_keywords:
 - KnownCompiler
 - dbgmodel/KnownCompiler
dev_langs:
 - c++
helpviewer_keywords:
 - KnownCompiler
---

## -description

The **KnownCompiler** enumeration identifies a well-known set of compilers.  

## -enum-fields

### -field CompilerUnknown

The compiler is unknown.   

### -field CompilerMSVC

The compiler is Microsoft Visual C++ (MSVC).  

### -field CompilerGCC

The compiler is GNU Compiler Collection (GCC). 

### -field CompilerClang

The compiler is Clang compiler.   

### -field CompilerRustC

The compiler is Rust compiler (rustc).   

## -remarks
      
These enum values can be used to identify which compiler is being used. 

## -see-also

[Debugger Data Model C++ Overview](/windows-hardware/drivers/debugger/data-model-cpp-overview)


