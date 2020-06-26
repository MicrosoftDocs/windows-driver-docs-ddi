---
UID: NC:wdbgexts.PSYM_DUMP_FIELD_CALLBACK
title: PSYM_DUMP_FIELD_CALLBACK (wdbgexts.h)
description: The PSYM_DUMP_FIELD_CALLBACK callback function is called by the debugger engine during the IG_DUMP_SYMBOL_INFO Ioctl operation with information about a member in the specified symbol.
old-location: debugger\psym_dump_field_callback.htm
tech.root: debugger
ms.assetid: 3a1d9751-194a-4eb7-86f1-f6e812b52f0c
ms.date: 03/26/2018
keywords: ["PSYM_DUMP_FIELD_CALLBACK callback"]
ms.keywords: PSYM_DUMP_FIELD_CALLBACK, PSYM_DUMP_FIELD_CALLBACK function pointer [Windows Debugging], WdbgExts_Ref_37493dec-e340-408d-8f7c-bda18057f427.xml, debugger.psym_dump_field_callback, wdbgexts/PSYM_DUMP_FIELD_CALLBACK
f1_keywords:
 - "wdbgexts/PSYM_DUMP_FIELD_CALLBACK"
req.header: wdbgexts.h
req.include-header:
req.target-type: Desktop
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
- UserDefined
api_location:
- wdbgexts.h
api_name:
- PSYM_DUMP_FIELD_CALLBACK
product:
- Windows
targetos: Windows
req.typenames: VPCI_WRITE_BLOCK_INPUT, *PVPCI_WRITE_BLOCK_INPUT
req.product: Windows 10 or later.
---

# PSYM_DUMP_FIELD_CALLBACK callback


## -description


The PSYM_DUMP_FIELD_CALLBACK callback function is called by the debugger engine during the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdbgexts/ns-wdbgexts-_sym_dump_param">IG_DUMP_SYMBOL_INFO</a> Ioctl operation with information about a member in the specified symbol.


## -parameters




### -param pField

Specifies the field for which this callback function is being called.  The debugger engine fills in the contents of this parameter before making the call.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdbgexts/ns-wdbgexts-_field_info">FIELD_INFO</a> for details about the members of this parameter.


### -param UserContext

Specifies the user context object passed to the <b>Ioctl</b> operation in the <b>Context</b> member of the SYM_DUMP_PARAM structure.


## -returns



If the function is successful, it should return STATUS_SUCCESS.  Otherwise, it should return an appropriate error code.




## -remarks



If you are writing a WdbgExts extension, include wdbgexts.h. If you are writing a DbgEng extension that uses this function prototype, include wdbgexts.h before dbgeng.h (see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/writing-dbgeng-extension-code">Writing DbgEng Extension Code</a> for details). STATUS_SUCCESS and other status and error codes are defined in ntstatus.h.





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdbgexts/ns-wdbgexts-_field_info">FIELD_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdbgexts/ns-wdbgexts-_sym_dump_param">IG_DUMP_SYMBOL_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdbgexts/nc-wdbgexts-pwindbg_ioctl_routine">Ioctl</a>
 

 

