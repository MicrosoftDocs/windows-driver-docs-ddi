---
UID: NF:wdbgexts.ReadPtr
title: ReadPtr function
author: windows-driver-content
description: The ReadPtr function reads a pointer from the target. ReadPointer should be used instead of this function as the return value of ReadPointer is more consistent with the rest of the WdbgExts API.
old-location: debugger\readptr.htm
old-project: debugger
ms.assetid: e3999ecc-9884-4ae6-8e01-be4538b1d53a
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: ReadPtr function [Windows Debugging], WdbgExts_Ref_4eaec659-6522-4d7f-b64a-ad771f93eb56.xml, debugger.readptr, wdbgexts/ReadPtr, ReadPtr
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdbgexts.h
req.include-header: Wdbgexts.h, Dbgeng.h
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdbgexts.h
apiname:
-	ReadPtr
product: Windows
targetos: Windows
req.typenames: EXT_TDOP
req.product: Windows 10 or later.
---

# ReadPtr function


## -description


The <b>ReadPtr</b> function reads a pointer from the target.  <a href="..\wdbgexts\nf-wdbgexts-readpointer.md">ReadPointer</a> should be used instead of this function as the return value of <b>ReadPointer</b> is more consistent with the rest of the WdbgExts API.


## -syntax


````
__inline ULONG ReadPtr(
   ULONG64  Addr,
   PULONG64 pPointer
);
````


## -parameters




### -param Addr

Specifies the address of the pointer to read.


### -param pPointer

Receives the value of the pointer.  If the target uses 32-bit pointers, the pointer is sign-extended to 64 bits.


## -returns



If the function succeeds, the return value is <b>FALSE</b>; otherwise, it is <b>TRUE</b>.




## -remarks



This function is identical to <a href="..\wdbgexts\nf-wdbgexts-readpointer.md">ReadPointer</a>, except the meaning of the return value is reversed.

If you are writing a WdbgExts extension, include <b>wdbgexts.h</b>. If you are writing a DbgEng extension that calls this function, include <b>wdbgexts.h</b> before <b>dbgeng.h</b> (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561480">Writing DbgEng Extension Code</a> for details).





## -see-also

<a href="..\wdbgexts\nf-wdbgexts-readpointer.md">ReadPointer</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ReadPtr function%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

