---
UID: NF:rxce.RxCeTearDownAddress
title: RxCeTearDownAddress function
author: windows-driver-content
description: RxCeTearDownAddress deregisters a transport address from a transport binding.
old-location: ifsk\rxceteardownaddress.htm
old-project: ifsk
ms.assetid: 76fd7c35-fef1-43c2-aedd-d09d18ab27a4
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: RxCeTearDownAddress
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: rxce.h
req.include-header: Rxce.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RxCeTearDownAddress
req.alt-loc: rxce.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= APC_LEVEL
req.typenames: *LPRILWRITEPHONEBOOKENTRYPARAMS, RILWRITEPHONEBOOKENTRYPARAMS
req.product: Windows 10 or later.
---

# RxCeTearDownAddress function



## -description
<b>RxCeTearDownAddress</b> deregisters a transport address from a transport binding.



## -syntax

````
NTSTATUS RxCeTearDownAddress(
  _In_ PRXCE_ADDRESS pAddress
);
````


## -parameters

### -param pAddress [in]

A pointer to the RDBSS connection engine address to deregister.


## -returns
<b>RxCeTearDownAddress</b> returns STATUS_SUCCESS on success or one of the following error codes on failure: 
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The <i>pAddress</i> parameter passed to <b>RxCeTearDownAddress</b> or one of the data members associated with this address was invalid. 

 


## -remarks
When <b>RxCeTearDownAddress</b> is successful, the data members in the RXCE_ADDRESS structure pointed to by the <i>pAddress</i> parameter will be properly uninitialized, TDI addresses will be closed, and allocated memory for handlers and transport addresses will be freed.


## -see-also
<dl>
<dt>
<a href="..\rxce\nf-rxce-rxcebuildaddress.md">RxCeBuildAddress</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxCeTearDownAddress function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

