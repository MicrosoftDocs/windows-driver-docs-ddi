---
UID: NS:wdbgexts._EXT_TYPED_DATA
title: _EXT_TYPED_DATA (wdbgexts.h)
description: The EXT_TYPED_DATA structure is passed to and returned from the DEBUG_REQUEST_EXT_TYPED_DATA_ANSI Request operation. It contains the input and output parameters for the operation as well as specifying which particular suboperation to perform.
old-location: debugger\ext_typed_data.htm
tech.root: debugger
ms.assetid: 99abb7b6-3e20-4875-b257-c3fc4146e392
ms.date: 05/03/2018
keywords: ["EXT_TYPED_DATA structure"]
ms.keywords: "*PEXT_TYPED_DATA, EXT_TYPED_DATA, EXT_TYPED_DATA structure [Windows Debugging], PEXT_TYPED_DATA, PEXT_TYPED_DATA structure pointer [Windows Debugging], Structures_e4240445-73f9-4f38-8f1b-17035ced15f7.xml, _EXT_TYPED_DATA, debugger.ext_typed_data, wdbgexts/EXT_TYPED_DATA, wdbgexts/PEXT_TYPED_DATA"
req.header: wdbgexts.h
req.include-header: WdbgExts.h, DbgEng.h
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
targetos: Windows
req.typenames: EXT_TYPED_DATA, *PEXT_TYPED_DATA
f1_keywords:
 - _EXT_TYPED_DATA
 - wdbgexts/_EXT_TYPED_DATA
 - PEXT_TYPED_DATA
 - wdbgexts/PEXT_TYPED_DATA
 - EXT_TYPED_DATA
 - wdbgexts/EXT_TYPED_DATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdbgexts.h
api_name:
 - EXT_TYPED_DATA
---

# _EXT_TYPED_DATA structure


## -description

The EXT_TYPED_DATA structure is passed to and returned from the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debug-request-ext-typed-data-ansi">DEBUG_REQUEST_EXT_TYPED_DATA_ANSI </a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugadvanced3-request">Request</a> operation. It contains the input and output parameters for the operation as well as specifying which particular suboperation to perform.

## -struct-fields

### -field Operation

Specifies which suboperation the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debug-request-ext-typed-data-ansi">DEBUG_REQUEST_EXT_TYPED_DATA_ANSI</a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugadvanced3-request">Request</a> operation should perform. The interpretation of some of the other members depends on <b>Operation</b>. For a list of possible suboperations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdbgexts/ne-wdbgexts-_ext_tdop">EXT_TDOP</a>.

### -field Flags

Specifies the bit flags describing the target's memory in which the data resides. If no flags are present, the data is considered to be in virtual memory. One of the following flags may be present:

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
EXT_TDF_PHYSICAL_DEFAULT

</td>
<td>
The typed data is in physical memory, and this physical memory uses the default memory caching.

</td>
</tr>
<tr>
<td>
EXT_TDF_PHYSICAL_CACHED

</td>
<td>
The typed data is in physical memory, and this physical memory is cached.

</td>
</tr>
<tr>
<td>
EXT_TDF_PHYSICAL_UNCACHED

</td>
<td>
The typed data is in physical memory, and this physical memory is uncached.

</td>
</tr>
<tr>
<td>
EXT_TDF_PHYSICAL_WRITE_COMBINED

</td>
<td>
The typed data is in physical memory, and this physical memory is write-combined.

</td>
</tr>
</table>

### -field InData

Specifies typed data to be used as input to the operation. For details about this structure, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdbgexts/ns-wdbgexts-_debug_typed_data">DEBUG_TYPED_DATA</a>.

The interpretation of <b>InData</b> depends on the value of <b>Operation</b>.

### -field OutData

Receives typed data as output from the operation. Any suboperation that returns typed data to <b>OutData</b> initially copies the contents of <b>InData</b> to <b>OutData</b>, then modifies <b>OutData</b> in place, so that the input parameters in <b>InData</b> are also present in <b>OutData</b>. For details about this structure, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdbgexts/ns-wdbgexts-_debug_typed_data">DEBUG_TYPED_DATA</a>.

The interpretation of <b>OutData</b> depends on the value of <b>Operation</b>.

### -field InStrIndex

Specifies the position of an ANSI string to be used as input to the operation. <b>InStrIndex</b> can be zero to indicate that the input parameters do not include an ANSI string.

The position of the string is relative to the base address of this EXT_TYPED_DATA structure. The string must follow this structure, so <b>InStrIndex</b> must be greater than the size of this structure. The string is part of the input to the operation and <b>InStrIndex</b> must be smaller than <i>InBufferSize</i>, the size of the input buffer passed to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugadvanced3-request">Request</a>.

The interpretation of the string depends on the value of <b>Operation</b>.

### -field In32

Specifies a 32-bit parameter to be used as input to the operation.

The interpretation of <b>In32</b> depends on the value of <b>Operation</b>.

### -field Out32

Receives a 32-bit value as output from the operation.

The interpretation of <b>Out32</b> depends on the value of <b>Operation</b>.

### -field In64

Specifies a 64-bit parameter to be used as input to the operation.

The interpretation of <b>In64</b> depends on the value of <b>Operation</b>.

### -field Out64

Receives a 64-bit value as output from the operation.

The interpretation of <b>Out64</b> depends on the value of <b>Operation</b>.

### -field StrBufferIndex

Specifies the position to return an ANSI string as output from the operation. <b>StrBufferIndex</b> can be zero if no ANSI string is to be received from the operation.

The position of the string is relative to the base address of the returned EXT_TYPED_DATA structure. The string must follow the structure, so <b>StrBufferIndex</b> must be greater than the size of this structure. The string is part of the output from the suboperation, and <b>StrBufferIndex</b> plus <b>StrBufferChars</b> must be smaller than <i>OutBufferSize</i>, the size of the output buffer passed to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugadvanced3-request">Request</a>.

The interpretation of the string depends on the value of <b>Operation</b>.

### -field StrBufferChars

Specifies the size in characters of the ANSI string buffer specified by <b>StrBufferIndex</b>.

### -field StrCharsNeeded

Receives the number of characters needed by the string buffer specified by <b>StrBufferIndex</b>.

### -field DataBufferIndex

Set to zero.

### -field DataBufferBytes

Set to zero.

### -field DataBytesNeeded

Set to zero,

### -field Status

Receives the status code returned by the operation. This is the same value returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugadvanced3-request">Request</a>.

### -field Reserved

Set to zero.

## -remarks

The members of this structure are used as the input and output parameters to the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debug-request-ext-typed-data-ansi">DEBUG_REQUEST_EXT_TYPED_DATA_ANSI </a>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugadvanced3-request">Request</a> operation. The interpretation of most of the parameters depends on the particular suboperation being performed, as specified by the <b>Operation</b> member.

This structure can optionally specify additional data--using the members <b>InStrIndex</b> and <b>StrBufferIndex</b>--that is included with the structure. This additional data is specified relative to the address of the instance of this structure. When used with the DEBUG_REQUEST_EXT_TYPED_DATA_ANSI <b>Request</b> operation, the additional data is included in the <i>InBuffer</i> and <i>OutBuffer</i> (as appropriate) and should be included in the size of these two buffers.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/debug-request-ext-typed-data-ansi">DEBUG_REQUEST_EXT_TYPED_DATA_ANSI</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdbgexts/ns-wdbgexts-_debug_typed_data">DEBUG_TYPED_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdbgexts/ne-wdbgexts-_ext_tdop">EXT_TDOP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nf-dbgeng-idebugadvanced3-request">Request</a>

