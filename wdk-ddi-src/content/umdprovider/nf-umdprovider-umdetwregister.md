---
UID: NF:umdprovider.UMDEtwRegister
title: UMDEtwRegister function
author: windows-driver-content
description: Registers the event trace provider. The driver should call this function before it makes any calls to log events.
old-location: display\umdetwregister.htm
old-project: display
ms.assetid: 03352d5d-122f-4818-965d-f5cc8231d6ed
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: UMDEtwRegister
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: umdprovider.h
req.include-header: Umdprovider.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UMDEtwRegister
req.alt-loc: umdprovider.h
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
req.typenames: UMDETW_ALLOCATION_SEMANTIC
req.product: Windows 10 or later.
---

# UMDEtwRegister function



## -description
Registers the event trace provider. The driver should call this function before it makes any calls to log events.



## -syntax

````
void UMDEtwRegister(
   PFNUMDETW_RUNDOWN CbRundown
);
````


## -parameters

### -param CbRundown 

A pointer to a callback function that returns information about the current state of the user-mode driver.

This callback function should call the <a href="..\umdprovider\nf-umdprovider-umdetwlogmapallocation.md">UMDEtwLogMapAllocation</a> function for every current allocation mapping.


## -returns
This function does not return a value.


## -remarks
The data type for the <i>CbRundown</i> parameter is defined as:

<b>UMDEtwRegister</b> is defined inline in Umdprovider.h as:

The <a href="https://msdn.microsoft.com/6025c3a6-7d88-49dc-bbc3-655c172dde3c">EventRegister</a> function and the <b>EVENT_CONTROL_CODE_XXX</b> values are  described in the <a href="https://msdn.microsoft.com/c10baa8d-50b9-4fda-89d0-d00b1d9f5404">Windows Events</a> documentation.


## -see-also
<dl>
<dt>
<a href="..\umdprovider\nf-umdprovider-umdetwlogmapallocation.md">UMDEtwLogMapAllocation</a>
</dt>
<dt>
<a href="..\umdprovider\nf-umdprovider-umdetwunregister.md">UMDEtwUnregister</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20UMDEtwRegister function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

