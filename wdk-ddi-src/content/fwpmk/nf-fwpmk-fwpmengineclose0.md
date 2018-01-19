---
UID: NF:fwpmk.FwpmEngineClose0
title: FwpmEngineClose0 function
author: windows-driver-content
description: The FwpmEngineClose0 function closes a previously opened session to the filter engine.Note  FwpmEngineClose0 is a specific version of FwpmEngineClose.
old-location: netvista\fwpmengineclose0.htm
old-project: netvista
ms.assetid: 79ac01ff-9976-4321-a6b1-0a1cc6e5810a
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: FwpmEngineClose0
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fwpmk.h
req.include-header: Fwpmk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FwpmEngineClose0
req.alt-loc: fwpkclnt.lib,fwpkclnt.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Fwpkclnt.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: PINSTANCE_PARTIAL_INFORMATION, INSTANCE_PARTIAL_INFORMATION
---

# FwpmEngineClose0 function



## -description
The 
  <b>FwpmEngineClose0</b> function closes a previously opened session to the filter engine.



## -syntax

````
NTSTATUS NTAPI FwpmEngineClose0(
  _Inout_ HANDLE engineHandle
);
````


## -parameters

### -param engineHandle [in, out]

A handle for an open session to the filter engine.


## -returns
The 
     <b>FwpmEngineClose0</b> function returns one of the following NTSTATUS codes.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The session to the filter engine was successfully closed.
<dl>
<dt><b>Other status codes</b></dt>
</dl>An error occurred.

 


## -remarks
A callout driver calls the 
    <b>FwpmEngineClose0</b> function to close a session to the filter engine that was previously opened by a
    call to the 
    <a href="..\fwpmk\nf-fwpmk-fwpmengineopen0.md">FwpmEngineOpen0</a> function.


## -see-also
<dl>
<dt>
<a href="..\fwpmk\nf-fwpmk-fwpmengineopen0.md">FwpmEngineOpen0</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpmEngineClose0 function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

