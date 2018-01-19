---
UID: NS:dbgeng._DEBUG_VALUE
title: _DEBUG_VALUE
author: windows-driver-content
description: The DEBUG_VALUE structure holds register and expression values.
old-location: debugger\debug_value.htm
old-project: debugger
ms.assetid: 568469ad-79c4-4437-aefe-a29e77e5143a
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _DEBUG_VALUE, DEBUG_VALUE, *PDEBUG_VALUE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dbgeng.h
req.include-header: DbgEng.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DEBUG_VALUE
req.alt-loc: dbgEng.h
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
req.typenames: DEBUG_VALUE, *PDEBUG_VALUE
---

# _DEBUG_VALUE structure



## -description
The DEBUG_VALUE structure holds register and expression values.



## -syntax

````
typedef struct _DEBUG_VALUE {
  union {
    UCHAR   I8;
    USHORT  I16;
    ULONG   I32;
    struct {
      ULONG64 I64;
      BOOL    Nat;
    };
    float   F32;
    double  F64;
    UCHAR   F80Bytes[10];
    UCHAR   F82Bytes[11];
    UCHAR   F128Bytes[16];
    UCHAR   VI8[16];
    USHORT  VI16[8];
    ULONG   VI32[4];
    ULONG64 VI64[2];
    float   VF32[4];
    double  VF64[2];
    struct {
      ULONG LowPart;
      ULONG HighPart;
    } I64Parts32;
    struct {
      ULONG64 LowPart;
      LONG64  HighPart;
    } F128Parts64;
    UCHAR   RawBytes[24];
  };
  ULONG TailOfRawBytes;
  ULONG Type;
}  DEBUG_VALUE, *PDEBUG_VALUE;
````


## -struct-fields

### -field ( unnamed union )

 


### -field I8

See Remarks.


### -field I16

See Remarks.


### -field I32

See Remarks.


### -field ( unnamed struct )

 


### -field I64

See Remarks.


### -field Nat

See Remarks.

</dd>
</dl>

### -field F32

See Remarks.


### -field F64

See Remarks.


### -field F80Bytes

See Remarks.


### -field F82Bytes

See Remarks.


### -field F128Bytes

See Remarks.


### -field VI8

See Remarks.


### -field VI16

See Remarks.


### -field VI32

See Remarks.


### -field VI64

See Remarks.


### -field VF32

See Remarks.


### -field VF64

See Remarks.


### -field I64Parts32

See Remarks.


### -field LowPart

See Remarks.


### -field HighPart

See Remarks.

</dd>
</dl>

### -field F128Parts64

See Remarks.


### -field LowPart

See Remarks.


### -field HighPart

See Remarks.

</dd>
</dl>

### -field RawBytes

See Remarks.

</dd>
</dl>

### -field TailOfRawBytes

See Remarks.


### -field Type

See Remarks.


## -remarks
The <b>Type</b> field specifies the value type that is being held by the structure. This also specifies which field in the structure is valid. The possible values of the <b>Type</b> field, and the corresponding field specified as valid in the structure, include the following.</p>