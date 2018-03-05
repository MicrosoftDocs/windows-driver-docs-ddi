---
UID: NF:bidispl.IBidiRequestContainer.GetRequestCount
title: IBidiRequestContainer::GetRequestCount method
author: windows-driver-content
description: The GetRequestCount method gets the number of requests in the request list.
old-location: print\ibidirequestcontainer_ibidirequestcontainer__getrequestcount.htm
old-project: print
ms.assetid: 4215ca86-9ceb-451d-8e67-992a8a3f9bab
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetRequestCount method [Print Devices], GetRequestCount method [Print Devices], IBidiRequestContainer interface, GetRequestCount,IBidiRequestContainer.GetRequestCount, IBidiRequestContainer, IBidiRequestContainer interface [Print Devices], GetRequestCount method, IBidiRequestContainer::GetRequestCount, _win32_IBidiRequestContainer_GetRequestCount, bidispl/IBidiRequestContainer::GetRequestCount, gdi.ibidirequestcontainer_ibidirequestcontainer__getrequestcount, print.ibidirequestcontainer_ibidirequestcontainer__getrequestcount
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: bidispl.h
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
-	IBidiRequestContainer.GetRequestCount
product: Windows
targetos: Windows
req.typenames: MPEG2_TRANSPORT_STRIDE, *PMPEG2_TRANSPORT_STRIDE
---

# IBidiRequestContainer::GetRequestCount method


## -description


The <b>GetRequestCount</b> method gets the number of requests in the request list.


## -syntax


````
HRESULT GetRequestCount(
  [out] ULONG *puCount
);
````


## -parameters




### -param puCount [out]

Pointer to a variable that receives the number of requests.


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
 




## -see-also

<a href="https://msdn.microsoft.com/b15b1aff-623e-4159-ab0f-ce386a1377eb">Bidirectional Communication Schema</a>



<a href="..\bidispl\nn-bidispl-ibidirequestcontainer.md">IBidiRequestContainer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545163">Bidirectional Communication Interfaces</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IBidiRequestContainer::GetRequestCount method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

