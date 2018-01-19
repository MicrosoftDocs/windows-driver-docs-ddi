---
UID: NF:fwpmk.FwpmBfeStateUnsubscribeChanges0
title: FwpmBfeStateUnsubscribeChanges0 function
author: windows-driver-content
description: The FwpmBfeStateUnsubscribeChanges0 function deregisters a base filtering engine (BFE) callback function that was previously registered by calling the FwpmBfeStateSubscribeChanges0 function.Note  FwpmBfeStateUnsubscribeChanges0 is a specific version of FwpmBfeStateUnsubscribeChanges. See WFP Version-Independent Names and Targeting Specific Versions of Windows for more information.
old-location: netvista\fwpmbfestateunsubscribechanges0.htm
old-project: netvista
ms.assetid: 1a84401a-d7da-43d2-925d-0d6ed370c980
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: FwpmBfeStateUnsubscribeChanges0
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
req.alt-api: FwpmBfeStateUnsubscribeChanges0
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

# FwpmBfeStateUnsubscribeChanges0 function



## -description
The 
  <b>FwpmBfeStateUnsubscribeChanges0</b> function deregisters a base filtering engine (BFE) callback function that was previously
  registered by calling the 
  <a href="..\fwpmk\nf-fwpmk-fwpmbfestatesubscribechanges0.md">
  FwpmBfeStateSubscribeChanges0</a> function.



## -syntax

````
NTSTATUS NTAPI FwpmBfeStateUnsubscribeChanges0(
  _Inout_ HANDLE changeHandle
);
````


## -parameters

### -param changeHandle [in, out]

A handle associated with the registration of the callback function that is being deregistered.
     This handle was returned to the callout driver when it called the 
     <a href="..\fwpmk\nf-fwpmk-fwpmbfestatesubscribechanges0.md">FwpmBfeStateSubscribeChanges0</a> function to register the callback function.


## -returns
The 
     <b>FwpmBfeStateUnsubscribeChanges0</b> function returns one of the following NTSTATUS codes:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The callback function was successfully deregistered.
<dl>
<dt><b>Other status codes</b></dt>
</dl>An error occurred.

 


## -remarks
A callout driver calls the 
    <b>FwpmBfeStateUnsubscribeChanges0</b> function to deregister a callback function that was previously
    registered by calling the 
    <a href="..\fwpmk\nf-fwpmk-fwpmbfestatesubscribechanges0.md">
    FwpmBfeStateSubscribeChanges0</a> function.

If a callout driver registers a callback function by calling the 
    <a href="..\fwpmk\nf-fwpmk-fwpmbfestatesubscribechanges0.md">
    FwpmBfeStateSubscribeChanges0</a> function, it must deregister the callback function before the callout
    driver can be unloaded.

Do not call <b>FwpmBfeStateUnsubscribeChanges0</b> from a callback function that your driver previously registered by calling <a href="..\fwpmk\nf-fwpmk-fwpmbfestatesubscribechanges0.md">
    FwpmBfeStateSubscribeChanges0</a>. Doing so can cause a deadlock.


## -see-also
<dl>
<dt>
<a href="..\fwpmk\nf-fwpmk-fwpmbfestatesubscribechanges0.md">
   FwpmBfeStateSubscribeChanges0</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpmBfeStateUnsubscribeChanges0 function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

