---
UID: NF:fwpmk.FwpmBfeStateGet0
title: FwpmBfeStateGet0 function
author: windows-driver-content
description: The FwpmBfeStateGet0 function retrieves the current state of the filter engine.Note  FwpmBfeStateGet0 is a specific version of FwpmBfeStateGet.
old-location: netvista\fwpmbfestateget0.htm
old-project: netvista
ms.assetid: f165c5a0-6f8e-495f-90b9-62d0d8982456
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: FwpmBfeStateGet0
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
req.alt-api: FwpmBfeStateGet0
req.alt-loc: Fwpkclnt.lib,Fwpkclnt.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Fwpkclnt.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: PINSTANCE_PARTIAL_INFORMATION, INSTANCE_PARTIAL_INFORMATION
---

# FwpmBfeStateGet0 function



## -description
The 
  <b>FwpmBfeStateGet0</b> function retrieves the current state of the filter engine.



## -syntax

````
FWPM_SERVICE_STATE NTAPI FwpmBfeStateGet0(void);
````


## -parameters


## -returns
The 
     <b>FwpmBfeStateGet0</b> function returns one of the following values.
<dl>
<dt><b>FWPM_SERVICE_STOPPED</b></dt>
</dl>The filter engine is not running.
<dl>
<dt><b>FWPM_SERVICE_START_PENDING</b></dt>
</dl>The filter engine is starting.
<dl>
<dt><b>FWPM_SERVICE_STOP_PENDING</b></dt>
</dl>The filter engine is stopping.
<dl>
<dt><b>FWPM_SERVICE_RUNNING</b></dt>
</dl>The filter engine is running.

 

The 
     <b>FwpmBfeStateGet0</b> function returns one of the following values.
<dl>
<dt><b>FWPM_SERVICE_STOPPED</b></dt>
</dl>The filter engine is not running.
<dl>
<dt><b>FWPM_SERVICE_START_PENDING</b></dt>
</dl>The filter engine is starting.
<dl>
<dt><b>FWPM_SERVICE_STOP_PENDING</b></dt>
</dl>The filter engine is stopping.
<dl>
<dt><b>FWPM_SERVICE_RUNNING</b></dt>
</dl>The filter engine is running.

 

The 
     <b>FwpmBfeStateGet0</b> function returns one of the following values.
<dl>
<dt><b>FWPM_SERVICE_STOPPED</b></dt>
</dl>The filter engine is not running.
<dl>
<dt><b>FWPM_SERVICE_START_PENDING</b></dt>
</dl>The filter engine is starting.
<dl>
<dt><b>FWPM_SERVICE_STOP_PENDING</b></dt>
</dl>The filter engine is stopping.
<dl>
<dt><b>FWPM_SERVICE_RUNNING</b></dt>
</dl>The filter engine is running.

 


## -remarks
A callout driver calls the 
    <b>FwpmBfeStateGet0</b> function to retrieve the current state of the filter engine. For a callout driver
    to open a session to the filter engine, the filter engine must  be currently running.

Before calling <b>FwpmBfeStateGet0</b>, the callout driver  must call the 
    <a href="..\fwpmk\nf-fwpmk-fwpmbfestatesubscribechanges0.md">FwpmBfeStateSubscribeChanges0</a> function to register a callback function that is called whenever the
    state of the filter engine changes.


## -see-also
<dl>
<dt>
<a href="..\fwpmk\nf-fwpmk-fwpmbfestatesubscribechanges0.md">
   FwpmBfeStateSubscribeChanges0</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpmBfeStateGet0 function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

