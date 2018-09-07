---
UID: NF:rxce.RxCeBuildConnection
title: RxCeBuildConnection function
author: windows-driver-content
description: RxCeBuildConnection establishes a connection between a local RDBSS connection address and a given remote address.
old-location: ifsk\rxcebuildconnection.htm
tech.root: ifsk
ms.assetid: 3d4c2e69-7cdc-4eee-b56c-b1485768e942
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: RxCeBuildConnection, RxCeBuildConnection function [Installable File System Drivers], ifsk.rxcebuildconnection, rxce/RxCeBuildConnection, rxref_cc87c9dd-c8e4-4283-96a8-bc2ec15be773.xml
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
req.lib: 
req.dll: 
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rxce.h
api_name:
-	RxCeBuildConnection
product:
- Windows
targetos: Windows
req.typenames: 
---

# RxCeBuildConnection function


## -description


<b>RxCeBuildConnection</b> establishes a connection between a local RDBSS connection address and a given remote address. 


## -parameters




### -param pLocalAddress

<p>A pointer to the local RDBSS connection engine address.</p>


### -param pConnectionInformation [in]

A pointer to the connection information that specifies the remote address.


### -param pHandler [in]

A pointer to the event handler for processing receive indications.


### -param pEventContext [in]

A pointer to the context parameter to be passed back to the event handler and used for indications.


### -param pConnection [in, out]

On input, this parameter contains a pointer to an uninitialized RDBSS connection. On output when this call is successful, the connection is properly initialized.


### -param pVc [in, out]

On input, this parameter contains a pointer to an uninitialized RDBSS virtual circuit. On output when this call is successful, the virtual circuit is associated with the connection and the virtual circuit is properly initialized.


#### - pAddress [in]

A pointer to the local RDBSS connection engine address.


## -returns



<b>RxCeBuildConnection</b> returns STATUS_SUCCESS on success or one of the following error codes on failure: 

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



<b>RxCeBuildConnection</b> should be called in the context of a system worker thread.

When <b>RxCeBuildConnection</b> is successful, the data members in the RXCE_CONNECTION structure pointed to by the <i>pConnection</i> parameter and the data members in the RXCE_VC structure pointed to by the <i>pVc</i> parameter will be properly initialized and the virtual circuit will be associated with the connection.

<b>RXCE_CONNECTION_INFORMATION</b> is a typedef for a <b>TDI_CONNECTION_INFORMATION</b> structure. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554321">RxCeTearDownConnection</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565085">TDI_CONNECTION_INFORMATION</a>
 

 

