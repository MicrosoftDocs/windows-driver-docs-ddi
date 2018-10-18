---
UID: NF:bidispl.IBidiRequestContainer.AddRequest
title: IBidiRequestContainer::AddRequest
author: windows-driver-content
description: The AddRequest method adds a request to the request list.
old-location: print\ibidirequestcontainer_ibidirequestcontainer__addrequest.htm
tech.root: print
ms.assetid: 69a97816-2994-4eec-b2ab-a545195e3776
ms.date: 4/20/2018
ms.keywords: AddRequest, AddRequest method [Print Devices], AddRequest method [Print Devices],IBidiRequestContainer interface, IBidiRequestContainer interface [Print Devices],AddRequest method, IBidiRequestContainer.AddRequest, IBidiRequestContainer::AddRequest, _win32_IBidiRequestContainer_AddRequest, bidispl/IBidiRequestContainer::AddRequest, gdi.ibidirequestcontainer_ibidirequestcontainer__addrequest, print.ibidirequestcontainer_ibidirequestcontainer__addrequest
ms.topic: method
req.header: bidispl.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows XP
req.target-min-winversvr: Windows Server 2003
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
req.dll: Bidispl.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	bidispl.dll
api_name:
-	IBidiRequestContainer.AddRequest
product:
- Windows
targetos: Windows
req.typenames: 
---

# IBidiRequestContainer::AddRequest


## -description


The <b>AddRequest</b> method adds a request to the request list.


## -parameters




### -param pRequest [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/dd144969">IBidiRequest</a> interface.


## -returns



The method returns one of the following values. For more information about COM error codes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff544310">Error Handling</a>.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The operation was successfully carried out.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
The interface handle was invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>None of the above</b></dt>
</dl>
</td>
<td width="60%">
The <b>HRESULT</b> contains an error code corresponding to the last error.

</td>
</tr>
</table>
 




## -remarks



This is similar to adding an item in a link list. In this case, <a href="https://msdn.microsoft.com/library/windows/hardware/dd144970">IBidiRequestContainer</a> will hold a reference to <i>pRequest</i> by calling pRequest-&gt;AddRef.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545163">Bidirectional Communication Interfaces</a>



<a href="https://msdn.microsoft.com/b15b1aff-623e-4159-ab0f-ce386a1377eb">Bidirectional Communication Schema</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dd144969">IBidiRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dd144970">IBidiRequestContainer</a>
 

 

