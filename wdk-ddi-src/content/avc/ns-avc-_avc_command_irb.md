---
UID: NS:avc._AVC_COMMAND_IRB
title: _AVC_COMMAND_IRB (avc.h)
description: The AVC_COMMAND_IRB structure defines a structure that contains an AV/C command and response pair.
old-location: stream\avc_command_irb.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["AVC_COMMAND_IRB structure"]
ms.keywords: "*PAVC_COMMAND_IRB, AVC_COMMAND_IRB, AVC_COMMAND_IRB structure [Streaming Media Devices], PAVC_COMMAND_IRB, PAVC_COMMAND_IRB structure pointer [Streaming Media Devices], _AVC_COMMAND_IRB, avc/AVC_COMMAND_IRB, avc/PAVC_COMMAND_IRB, avcref_1f88c208-64b9-40d1-9048-d10b105b5569.xml, stream.avc_command_irb"
req.header: avc.h
req.include-header: Avc.h
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
req.typenames: AVC_COMMAND_IRB, *PAVC_COMMAND_IRB
f1_keywords:
 - _AVC_COMMAND_IRB
 - avc/_AVC_COMMAND_IRB
 - PAVC_COMMAND_IRB
 - avc/PAVC_COMMAND_IRB
 - AVC_COMMAND_IRB
 - avc/AVC_COMMAND_IRB
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - avc.h
api_name:
 - AVC_COMMAND_IRB
---

# _AVC_COMMAND_IRB structure


## -description

The AVC_COMMAND_IRB structure defines a structure that contains an AV/C command and response pair.

## -struct-fields

### -field Common

This must be set to the <b>AVC_FUNCTION_COMMAND</b> enumerator from the AVC_FUNCTION enumeration.

### -field SubunitAddrFlag

This is a flag indicating if the <b>SubunitAddr</b> member specifies an address. Set to one if it does, otherwise set to zero.

### -field AlternateOpcodesFlag

This is a flag indicating if the <b>AlternateOpcodes</b> member is valid. Set to one if it is, otherwise set to zero.

### -field TimeoutFlag

Set this to one if the default time-out is not appropriate for the subunit. If this is set, the <b>Timeout</b> member must be set to the desired time-out (in 100-ns units).

### -field RetryFlag

Set this to one if the default retry count is not appropriate for the subunit. If this is set, the <b>Retries</b> member must be set to the desired retry count.

### -field CommandType

This specifies a value from the AvcCommandType enumeration. This member is used only during AVC_FUNCTION_GET_REQUEST. It is ignored otherwise.

### -field ResponseCode

This specifies a value from the AvcResponseCode enumeration. This member is used only during AVC_FUNCTION_SEND_RESPONSE. It is ignored otherwise.

### -field SubunitAddr

Set this to the address of nonpaged memory containing the desired subunit address encoded according to Section 5.3.3 of the AV/C Digital Interface Command Set General Specification, Rev 3.0. This specification can be found at the <a href="https://go.microsoft.com/fwlink/p/?linkid=8728">1394 Trade Association</a> website. No length is necessary because the subunit address encoding implies this. This parameter is ignored if <b>SubunitAddrFlag</b> is zero.

### -field AlternateOpcodes

Set this to the address of nonpaged memory containing the desired alternate opcode list. The first byte of the opcode list is the count of opcodes to follow (equivalent to the number of bytes). The total length of the memory containing the alternate opcode list is AlternateOpcodes[0]+1. This parameter is ignored if <b>AlternateOpcodesFlag</b> is zero.

### -field Timeout

Set this to the desired time-out in 100-ns units. For example, the default time-out value is: <b>Timeout.QuadPart</b> = 1000000 (100ms in 100ns units). This parameter is ignored if <b>TimeoutFlag</b> is zero.

### -field Retries

Set this to the desired number of times <i>avc.sys</i> should attempt to retry requests after each time-out without a response. Note that a retry count of zero means that the request is tried once. The total amount of time spent trying to process a command without getting a response is Timeout * (Retries + 1). This parameter is ignored if <b>RetryFlag</b> is zero.

### -field Opcode

Set this to the desired AV/C opcode (appropriate for the subunit type). This is a required parameter. On response, if <b>AlternateOpcodesFlag</b> was set, and one of the alternate opcodes was used to match the response, this is set to that alternate opcode.

### -field OperandLength

Set this to the number of bytes used to store the operands in the <b>Operands</b> member. This is a required parameter. On response, this parameter is set to the number of bytes in the operand list used by the response.

### -field Operands

Set this to the operand list appropriate for the subunit type and opcode. This is a required parameter. On response, this parameter contains the operand list of the response.

### -field NodeAddress

Reserved. This member must be zero.

### -field Generation

Reserved. This member must be zero.

## -remarks

This structure is used with the <a href="/windows-hardware/drivers/stream/avc-function-command">AVC_FUNCTION_COMMAND</a>, <a href="/windows-hardware/drivers/stream/avc-function-get-request">AVC_FUNCTION_GET_REQUEST</a> and <a href="/windows-hardware/drivers/stream/avc-function-send-response">AVC_FUNCTION_SEND_RESPONSE</a> function codes.

## -see-also

<a href="/windows-hardware/drivers/ddi/avc/ne-avc-_tagavc_function">AVC_FUNCTION</a>



<a href="/windows-hardware/drivers/stream/avc-function-command">AVC_FUNCTION_COMMAND</a>



<a href="/windows-hardware/drivers/stream/avc-function-get-request">AVC_FUNCTION_GET_REQUEST</a>



<a href="/windows-hardware/drivers/stream/avc-function-send-response">AVC_FUNCTION_SEND_RESPONSE</a>
