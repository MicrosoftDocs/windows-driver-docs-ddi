---
UID: NF:dbgeng.IDebugClient5.SetOutputCallbacksWide
title: IDebugClient5::SetOutputCallbacksWide method
author: windows-driver-content
description: The SetOutputCallbacksWide method registers an output callbacks object with this client.
old-location: debugger\setoutputcallbackswide.htm
old-project: debugger
ms.assetid: cd6f68b2-2a62-4607-8c70-11a94fd75ecb
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: SetOutputCallbacksWide, debugger.setoutputcallbackswide, IDebugClient5, dbgeng/IDebugClient5::SetOutputCallbacksWide, IDebugClient5 interface [Windows Debugging], SetOutputCallbacksWide method, SetOutputCallbacksWide method [Windows Debugging], IDebugClient5 interface, SetOutputCallbacksWide method [Windows Debugging], IDebugClient5::SetOutputCallbacksWide
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
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
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugClient5.SetOutputCallbacksWide
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugClient5::SetOutputCallbacksWide method


## -description


The <b>SetOutputCallbacksWide</b> method registers an <a href="https://msdn.microsoft.com/7a23ee09-0314-400a-8152-eef49a225427">output callbacks</a> object with this client.


## -syntax


````
HRESULT SetOutputCallbacksWide(
  [in] PDEBUG_OUTPUT_CALLBACKS_WIDE Callbacks
);
````


## -parameters




### -param Callbacks [in]

Specifies the interface pointer to the output callbacks object to register with this client.


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



Each client can have at most one <a href="..\dbgeng\nn-dbgeng-idebugoutputcallbacks.md">IDebugOutputCallbacks</a> or <b>IDebugOutputCallbacksWide</b> object registered with it for output.

The <b>IDebugOutputCallbacksWide</b> interface extends the COM interface <b>IUnknown</b>.  <b>SetOutputCallbacks</b> and <b>SetOutputCAllbacksWide</b> call the <b>IUnknown::AddRef</b> method in the object specified by <i>Callbacks</i>.  The <b>IUnknown::Release</b> method of this interface will be called the next time <b>SetOutputCallbacks</b> or <b>SetOutputCallbacksWide</b> is called on this client, or when this client is deleted. 

For more information about callbacks, see <a href="https://msdn.microsoft.com/9090a465-b6ab-4e99-8155-b0abdb729468">Callbacks</a>.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugoutputcallbacks.md">IDebugOutputCallbacks</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548071">GetOutputCallbacks</a>



<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient5::SetOutputCallbacksWide method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

