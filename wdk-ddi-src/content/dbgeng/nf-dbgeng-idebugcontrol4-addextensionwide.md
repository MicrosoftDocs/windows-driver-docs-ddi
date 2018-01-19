---
UID: NF:dbgeng.IDebugControl4.AddExtensionWide
title: IDebugControl4::AddExtensionWide method
author: windows-driver-content
description: The AddExtensionWide method loads an extension library into the debugger engine.
old-location: debugger\addextensionwide.htm
old-project: debugger
ms.assetid: 5c918f44-1ee7-4666-b83a-e13ce02e26db
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugControl4, IDebugControl4::AddExtensionWide, AddExtensionWide
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
req.alt-api: IDebugControl4.AddExtensionWide
req.alt-loc: Dbgeng.h
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

# IDebugControl4::AddExtensionWide method



## -description
The <b>AddExtensionWide</b>  method loads an extension library into the <a href="debugger.introduction#debugger_engine#debugger_engine">debugger engine</a>.



## -syntax

````
HRESULT AddExtensionWide(
  [in]  PCSTR    Path,
  [in]  ULONG    Flags,
  [out] PULONG64 Handle
);
````


## -parameters

### -param Path [in]

Specifies the fully qualified path and file name of the extension library to load.


### -param Flags [in]

Set to zero.


### -param Handle [out]

Receives the handle of the loaded extension library.


## -returns
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 

This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.


## -remarks
If the extension library has already been loaded, the handle to already loaded library is returned.  The extension library is not loaded again.

The extension library is loaded into the host engine and <i>Path</i> contains a path and file name for this instance of the debugger engine.

For more information on using extension libraries, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539033">Calling Extensions and Extension Functions</a>.


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol4.md">IDebugControl4</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554497">RemoveExtension</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546717">GetExtensionByPath</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl4::AddExtensionWide method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

