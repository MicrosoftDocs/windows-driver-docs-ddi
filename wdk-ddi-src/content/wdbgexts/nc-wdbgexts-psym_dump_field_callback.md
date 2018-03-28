---
UID: NC:wdbgexts.PSYM_DUMP_FIELD_CALLBACK
title: PSYM_DUMP_FIELD_CALLBACK
author: windows-driver-content
description: The PSYM_DUMP_FIELD_CALLBACK callback function is called by the debugger engine during the IG_DUMP_SYMBOL_INFO Ioctl operation with information about a member in the specified symbol.
old-location: debugger\psym_dump_field_callback.htm
old-project: debugger
ms.assetid: 3a1d9751-194a-4eb7-86f1-f6e812b52f0c
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: PSYM_DUMP_FIELD_CALLBACK, PSYM_DUMP_FIELD_CALLBACK function pointer [Windows Debugging], WdbgExts_Ref_37493dec-e340-408d-8f7c-bda18057f427.xml, debugger.psym_dump_field_callback, wdbgexts/PSYM_DUMP_FIELD_CALLBACK
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	wdbgexts.h
api_name:
-	PSYM_DUMP_FIELD_CALLBACK
product: Windows
targetos: Windows
req.typenames: VPCI_WRITE_BLOCK_INPUT, *PVPCI_WRITE_BLOCK_INPUT
req.product: Windows 10 or later.
---

# PSYM_DUMP_FIELD_CALLBACK callback


## -description


The PSYM_DUMP_FIELD_CALLBACK callback function is called by the debugger engine during the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550906">IG_DUMP_SYMBOL_INFO</a> Ioctl operation with information about a member in the specified symbol.


## -parameters




### -param *pField

Specifies the field for which this callback function is being called.  The debugger engine fills in the contents of this parameter before making the call.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff545316">FIELD_INFO</a> for details about the members of this parameter.


### -param UserContext

Specifies the user context object passed to the <b>Ioctl</b> operation in the <b>Context</b> member of the SYM_DUMP_PARAM structure.


## -returns



If the function is successful, it should return STATUS_SUCCESS.  Otherwise, it should return an appropriate error code.




## -remarks



If you are writing a WdbgExts extension, include wdbgexts.h. If you are writing a DbgEng extension that uses this function prototype, include wdbgexts.h before dbgeng.h (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561480">Writing DbgEng Extension Code</a> for details). STATUS_SUCCESS and other status and error codes are defined in ntstatus.h.





## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545316">FIELD_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550906">IG_DUMP_SYMBOL_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551084">Ioctl</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20PSYM_DUMP_FIELD_CALLBACK function pointer%20 RELEASE:%20(3/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

