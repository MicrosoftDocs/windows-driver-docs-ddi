---
UID: NS:avc._AVC_COMMAND_IRB
title: "_AVC_COMMAND_IRB"
author: windows-driver-content
description: The AVC_COMMAND_IRB structure defines a structure that contains an AV/C command and response pair.
old-location: stream\avc_command_irb.htm
old-project: stream
ms.assetid: 0aefbce4-a838-40c4-b31f-ff8dd13621f7
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: PAVC_COMMAND_IRB, AVC_COMMAND_IRB structure [Streaming Media Devices], _AVC_COMMAND_IRB, stream.avc_command_irb, avcref_1f88c208-64b9-40d1-9048-d10b105b5569.xml, *PAVC_COMMAND_IRB, avc/AVC_COMMAND_IRB, avc/PAVC_COMMAND_IRB, AVC_COMMAND_IRB, PAVC_COMMAND_IRB structure pointer [Streaming Media Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	avc.h
apiname:
-	AVC_COMMAND_IRB
product: Windows
targetos: Windows
req.typenames: "*PAVC_COMMAND_IRB, AVC_COMMAND_IRB"
---

# _AVC_COMMAND_IRB structure


## -description


The AVC_COMMAND_IRB structure defines a structure that contains an AV/C command and response pair.


## -syntax


````
typedef struct _AVC_COMMAND_IRB {
  AVC_IRB       Common;
  UCHAR         SubunitAddrFlag  :1;
  UCHAR         AlternateOpcodesFlag  :1;
  UCHAR         TimeoutFlag  :1;
  UCHAR         RetryFlag  :1;
  union {
    UCHAR CommandType;
    UCHAR ResponseCode;
  };
  PUCHAR        SubunitAddr;
  PUCHAR        AlternateOpcodes;
  LARGE_INTEGER Timeout;
  UCHAR         Retries;
  UCHAR         Opcode;
  ULONG         OperandLength;
  UCHAR         Operands[MAX_AVC_OPERAND_BYTES];
  NODE_ADDRESS  NodeAddress;
  ULONG         Generation;
} AVC_COMMAND_IRB, *PAVC_COMMAND_IRB;
````


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


### -field SubunitAddr

Set this to the address of nonpaged memory containing the desired subunit address encoded according to Section 5.3.3 of the AV/C Digital Interface Command Set General Specification, Rev 3.0. This specification can be found at the <a href="http://go.microsoft.com/fwlink/p/?linkid=8728">1394 Trade Association</a> website. No length is necessary because the subunit address encoding implies this. This parameter is ignored if <b>SubunitAddrFlag</b> is zero.


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


#### - CommandType

This specifies a value from the AvcCommandType enumeration. This member is used only during AVC_FUNCTION_GET_REQUEST. It is ignored otherwise.


#### - ResponseCode

This specifies a value from the AvcResponseCode enumeration. This member is used only during AVC_FUNCTION_SEND_RESPONSE. It is ignored otherwise.


## -remarks



This structure is used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554150">AVC_FUNCTION_COMMAND</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff554163">AVC_FUNCTION_GET_REQUEST</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff554170">AVC_FUNCTION_SEND_RESPONSE</a> function codes.




## -see-also

<a href="..\avc\ne-avc-_tagavc_function.md">AVC_FUNCTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554163">AVC_FUNCTION_GET_REQUEST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554170">AVC_FUNCTION_SEND_RESPONSE</a>



<a href="..\avc\ne-avc-_tagavc_function.md">AVC_FUNCTION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20AVC_COMMAND_IRB structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

