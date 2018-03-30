---
UID: NF:dbgeng.IDebugClient.SetOutputLinePrefix
title: IDebugClient::SetOutputLinePrefix method
author: windows-driver-content
description: Sets a prefix for multiple lines of output.
old-location: debugger\idebugclient_setoutputlineprefix.htm
old-project: debugger
ms.assetid: 59A3FD7D-153D-4580-84C1-2408A485F684
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: IDebugClient, IDebugClient interface [Windows Debugging], SetOutputLinePrefix method, IDebugClient::SetOutputLinePrefix, SetOutputLinePrefix method [Windows Debugging], SetOutputLinePrefix method [Windows Debugging], IDebugClient interface, SetOutputLinePrefix,IDebugClient.SetOutputLinePrefix, dbgeng/IDebugClient::SetOutputLinePrefix, debugger.idebugclient_setoutputlineprefix
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugClient.SetOutputLinePrefix
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugClient::SetOutputLinePrefix method


## -description


    Sets a prefix for multiple lines of output. 


## -parameters




### -param Prefix [in, optional]

A pointer to the prefix value.


## -returns



This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.

</td>
</tr>
</table>
 




## -remarks



Some of the engine commands produce
    multiple lines of output.  This function sets a prefix that the engine adds to each line. This function allows the caller to control indentation or identifying marks.

 The prefix value  is not a general setting for any output
    that contains a newline. Methods which use
    the line prefix are marked in their documentation.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549827">IDebugClient</a>
 

 

