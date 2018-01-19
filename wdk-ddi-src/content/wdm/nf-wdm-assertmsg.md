---
UID: NF:wdm.ASSERTMSG
title: ASSERTMSG macro
author: windows-driver-content
description: ASSERTMSG tests an expression. If the expression is false, it breaks into the kernel debugger and sends it the specified message.
old-location: devtest\assertmsg.htm
old-project: devtest
ms.assetid: 88c0cd30-607b-48f4-b2b6-3c21be1ce31a
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ASSERTMSG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows 2000 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ASSERTMSG
req.alt-loc: ntddk.h
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
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ASSERTMSG macro



## -description
<b>ASSERTMSG</b> tests an expression. If the expression is false, it breaks into the kernel debugger and sends it the specified message.



## -syntax

````
VOID ASSERTMSG(
    Message,
    Expression
);
````


## -parameters

### -param Message 

Specifies the null-delimited string to be displayed by the debugger.


### -param Expression 

Specifies any logical expression.


## -remarks
<b>ASSERTMSG</b> is identical to <b>ASSERT</b>, except that it sends an additional message to the debugger.

This macro will only be included in your binary if your code is compiled in a Debug configuration. Once your driver is built, <b>ASSERTMSG</b> will work properly regardless of whether your driver is run on the checked build or on the free build of Windows. 

If <i>Expression</i> evaluates to <b>TRUE</b>, this routine has no effect.

If <i>Expression</i> evaluates to <b>FALSE</b>, a message is displayed in the Debugger Command window. The message contains the source-code string of <i>Expression</i>, as well as the path of the source-code file and the line number of the instruction that called the macro. In this event, <b>ASSERTMSG</b> can be ignored and the process or thread in which <b>ASSERTMSG</b> occurred can be terminated. Alternatively, the debugger can be used to analyze the situation or to edit memory. If <b>ASSERTMSG</b> is ignored, execution continues as if the <b>g (Go)</b> command was entered.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff542107">ASSERT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [devtest\devtest]:%20ASSERTMSG function%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

