---
UID: NF:rxce.RxCeBuildVC
title: RxCeBuildVC function
author: windows-driver-content
description: RxCeBuildVC adds a virtual circuit to a specified RDBSS connection..
old-location: ifsk\rxcebuildvc.htm
old-project: ifsk
ms.assetid: b060bd22-113f-4f78-8763-d1d19cf198b8
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: RxCeBuildVC, rxce/RxCeBuildVC, RxCeBuildVC function [Installable File System Drivers], rxref_4f4f58c7-5970-4a86-883e-359e92bddaa3.xml, ifsk.rxcebuildvc
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
-	RxCeBuildVC
product: Windows
targetos: Windows
req.typenames: "*LPRILWRITEPHONEBOOKENTRYPARAMS, RILWRITEPHONEBOOKENTRYPARAMS"
req.product: Windows 10 or later.
---

# RxCeBuildVC function


## -description


<b>RxCeBuildVC</b> adds a virtual circuit to a specified RDBSS connection..


## -syntax


````
NTSTATUS RxCeBuildVC(
  _Inout_ PRXCE_VC         pVc,
  _In_    PRXCE_CONNECTION pConnection
);
````


## -parameters




### -param pVc [in, out]

On input, this parameter contains a pointer to a handle for an uninitialized virtual circuit. On output when this call is successful, the virtual circuit is associated with the specified connection and the state of the virtual circuit is initialized as active.


### -param Connection

TBD



#### - pConnection [in]

A pointer to the connection on which the virtual circuit is to be added.


## -returns


<b>RxCeBuildVC</b> returns STATUS_SUCCESS on success or one of the following error codes on failure: 
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The allocation of nonpaged pool memory needed by this routine failed. 

</td>
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


When <b>RxCeBuildVC</b> is successful, the data members in the RXCE_VC structure pointed to by the <i>pVC</i> parameter will be properly initialized and the virtual circuit will be added to the specified RDBSS connection. 



## -see-also

<a href="..\rxce\nf-rxce-rxceteardownvc.md">RxCeTearDownVC</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxCeBuildVC function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

