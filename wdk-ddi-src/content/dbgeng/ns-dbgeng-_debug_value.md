---
UID: NS:dbgeng._DEBUG_VALUE
title: _DEBUG_VALUE (dbgeng.h)
description: The DEBUG_VALUE structure holds register and expression values.
old-location: debugger\debug_value.htm
tech.root: debugger
ms.assetid: 568469ad-79c4-4437-aefe-a29e77e5143a
ms.date: 05/03/2018
ms.keywords: "*PDEBUG_VALUE, DEBUG_VALUE, DEBUG_VALUE structure [Windows Debugging], PDEBUG_VALUE, PDEBUG_VALUE structure pointer [Windows Debugging], Structures_2486f31c-2a25-41eb-ac3f-9cc1d62dd2e0.xml, _DEBUG_VALUE, dbgeng/DEBUG_VALUE, dbgeng/PDEBUG_VALUE, debugger.debug_value"
ms.topic: struct
req.header: dbgeng.h
req.include-header: DbgEng.h
req.target-type: Windows
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- dbgEng.h
api_name:
- DEBUG_VALUE
product:
- Windows
targetos: Windows
req.typenames: DEBUG_VALUE, *PDEBUG_VALUE
---

# _DEBUG_VALUE structure


## -description


The DEBUG_VALUE structure holds register and expression values.


## -struct-fields




### -field I8

 


### -field I16

 


### -field I32

 


### -field I64

 


### -field Nat

 


### -field F32

 


### -field F64

 


### -field F80Bytes

 


### -field F82Bytes

 


### -field F128Bytes

 


### -field VI8

 


### -field VI16

 


### -field VI32

 


### -field VI64

 


### -field VF32

 


### -field VF64

 


### -field I64Parts32

 


### -field I64Parts32.LowPart

 


### -field I64Parts32.HighPart

 


### -field F128Parts64

 


### -field F128Parts64.LowPart

 


### -field F128Parts64.HighPart

 


### -field RawBytes

 


### -field TailOfRawBytes

See Remarks.


### -field Type

See Remarks.


#### - ( unnamed union )

 



#### I8

See Remarks.



#### I16

See Remarks.



#### I32

See Remarks.



#### ( unnamed struct )

 



##### I64

See Remarks.



##### Nat

See Remarks.



#### F32

See Remarks.



#### F64

See Remarks.



#### F80Bytes

See Remarks.



#### F82Bytes

See Remarks.



#### F128Bytes

See Remarks.



#### VI8

See Remarks.



#### VI16

See Remarks.



#### VI32

See Remarks.



#### VI64

See Remarks.



#### VF32

See Remarks.



#### VF64

See Remarks.



#### I64Parts32

See Remarks.



##### LowPart

See Remarks.



##### HighPart

See Remarks.



#### F128Parts64

See Remarks.



##### LowPart

See Remarks.



##### HighPart

See Remarks.



#### RawBytes

See Remarks.


## -remarks



The <b>Type</b> field specifies the value type that is being held by the structure. This also specifies which field in the structure is valid. The possible values of the <b>Type</b> field, and the corresponding field specified as valid in the structure, include the following.

<table>
<tr>
<th>Type Name</th>
<th>Type</th>
<th>Valid DEBUG_VALUE Field</th>
</tr>
<tr>
<td>DEBUG_VALUE_INT8</td>
<td>8-bit signed integer</td>
<td><b>I8</b></td>
</tr>
<tr>
<td>DEBUG_VALUE_INT16</td>
<td>16-bit signed integer</td>
<td><b>I16</b></td>
</tr>
<tr>
<td>DEBUG_VALUE_INT32</td>
<td>32-bit signed integer</td>
<td><b>I32</b></td>
</tr>
<tr>
<td>DEBUG_VALUE_INT64</td>
<td>64-bit signed integer</td>
<td><b>I64</b></td>
</tr>
<tr>
<td>DEBUG_VALUE_FLOAT32</td>
<td>32-bit floating point number</td>
<td><b>F32</b></td>
</tr>
<tr>
<td>DEBUG_VALUE_FLOAT64</td>
<td>64-bit floating point number</td>
<td><b>F64</b></td>
</tr>
<tr>
<td>DEBUG_VALUE_FLOAT80</td>
<td>80-bit floating point number</td>
<td><b>F80Bytes</b></td>
</tr>
<tr>
<td>DEBUG_VALUE_FLOAT128</td>
<td>128-bit floating point number</td>
<td><b>F128Bytes</b></td>
</tr>
<tr>
<td>DEBUG_VALUE_VECTOR64</td>
<td>64-bit vector</td>
<td><b>VI8[8]</b>, <b>VI16[4]</b>, <b>VI32[2]</b>, <b>VI64[1]</b>, <b>VF32[2]</b>, <b>VF64[1]</b></td>
</tr>
<tr>
<td>DEBUG_VALUE_VECTOR128</td>
<td>128-bit vector</td>
<td><b>VI8[16]</b>, <b>VI16[8]</b>, <b>VI32[4]</b>, <b>VI64[2]</b>, <b>VF32[4]</b>, <b>VF64[2]</b></td>
</tr>
</table>
 



