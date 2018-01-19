---
UID: NF:dbgeng.IDebugSystemObjects4.SetCurrentSystemId
title: IDebugSystemObjects4::SetCurrentSystemId method
author: windows-driver-content
description: The SetCurrentSystemId method makes the specified target the current target.
old-location: debugger\setcurrentsystemid.htm
old-project: debugger
ms.assetid: 95b761ff-ca78-4793-b5eb-a9ff35a963d3
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSystemObjects4, IDebugSystemObjects4::SetCurrentSystemId, SetCurrentSystemId
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
req.alt-api: IDebugSystemObjects3.SetCurrentSystemId,IDebugSystemObjects4.SetCurrentSystemId
req.alt-loc: dbgeng.h
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
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
---

# IDebugSystemObjects4::SetCurrentSystemId method



## -description
The <b>SetCurrentSystemId</b> method makes the specified target the current target.



## -syntax

````
HRESULT SetCurrentSystemId(
  [in] ULONG Id
);
````


## -parameters

### -param Id [in]

Specifies the engine target ID for the target that is to become the current target.


## -returns
This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>No process with the given ID was found.

 


## -remarks
This method also sets the current thread and current process, and may change the current computer.

If the current target is changed, the callback <a href="https://msdn.microsoft.com/library/windows/hardware/ff550683">IDebugEventCallbacks::ChangeEngineState</a> will be called with the DEBUG_CES_CURRENT_THREAD bit set.


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugsystemobjects3.md">IDebugSystemObjects3</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugsystemobjects4.md">IDebugSystemObjects4</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541386">Debugging Session and Execution Model</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSystemObjects3::SetCurrentSystemId method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

