---
UID: NF:rxce.RxCeTearDownVC
title: RxCeTearDownVC function
author: windows-driver-content
description: RxCeTearDownVC deregisters a virtual circuit from a specified RDBSS connection.
old-location: ifsk\rxceteardownvc.htm
old-project: ifsk
ms.assetid: d4b3af4d-8bb2-42a4-a8d9-baa643a90418
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RxCeTearDownVC, rxce/RxCeTearDownVC, rxref_12c4b02d-b629-4543-bf74-aeaa14f6f05d.xml, ifsk.rxceteardownvc, RxCeTearDownVC function [Installable File System Drivers]
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rxce.h
apiname:
-	RxCeTearDownVC
product: Windows
targetos: Windows
req.typenames: RILWRITEPHONEBOOKENTRYPARAMS, *LPRILWRITEPHONEBOOKENTRYPARAMS
req.product: Windows 10 or later.
---

# RxCeTearDownVC function


## -description


<b>RxCeTearDownVC</b> deregisters a virtual circuit from a specified RDBSS connection.


## -syntax


````
NTSTATUS RxCeTearDownVC(
  _In_ PRXCE_VC pVc
);
````


## -parameters




### -param pVc [in]

A pointer to a handle for an virtual circuit structure to be torn down. 


## -returns



<b>RxCeTearDownVC</b> returns STATUS_SUCCESS on success or one of the following error codes on failure: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
One of the parameters passed to this routine was invalid. 

</td>
</tr>
</table>
 




## -remarks



When <b>RxCeTearDownVC</b> is successful, the data members in the RXCE_VC structure pointed to by the <i>pVC</i> parameter will be properly uninitialized and the virtual circuit will be disconnected from the associated RDBSS transport, address, and connection. 

Note that <b>RxCeTearDownVC</b> will wait for the clean up of connections over other transports to be completed before returning.

<b>RxCeTearDownVC</b> calls TDI to disconnect the virtual circuit associated with a connection. If the call to TDI is unsuccessful, <b>RxCeTearDownVC</b> will return the error from the TDI routine call. 




## -see-also

<a href="..\rxce\nf-rxce-rxcebuildvc.md">RxCeBuildVC</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxCeTearDownVC function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

