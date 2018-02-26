---
UID: NF:hbaapi.HBA_GetFcpTargetMapping
title: HBA_GetFcpTargetMapping function
author: windows-driver-content
description: The HBA_GetFcpTargetMapping routine retrieves the mappings between operating system and fibre channel protocol (FCP) identifiers for a set of targets that the HBA can enumerate.
old-location: storage\hba_getfcptargetmapping.htm
old-project: storage
ms.assetid: d1064f97-e640-49b6-be8c-19662e5de9bb
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , A, B, F, G, H, HBA_GetFcpTargetMapping, HBA_GetFcpTargetMapping routine [Storage Devices], M, T, _, a, c, e, fibreHBA_rtns_352928a8-39d5-4989-8156-0b1025b59350.xml, g, hbaapi/HBA_GetFcpTargetMapping, i, n, p, r, storage.hba_getfcptargetmapping, t"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: hbaapi.h
req.include-header: Hbaapi.h
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
req.lib: Hbaapi.lib
req.dll: Hbaapi.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Hbaapi.dll
apiname:
-	HBA_GetFcpTargetMapping
product: Windows
targetos: Windows
req.typenames: HBA_WWNTYPE
---

# HBA_GetFcpTargetMapping function


## -description


The <b>HBA_GetFcpTargetMapping</b> routine retrieves the mappings between operating system and fibre channel protocol (FCP) identifiers for a set of targets that the HBA can enumerate.


## -syntax


````
HBA_STATUS HBA_API HBA_GetFcpTargetMapping(
  _In_    HBA_HANDLE            HbaHandle,
  _Inout_ PHBA_FCPTARGETMAPPING Mapping
);
````


## -parameters




### -param Handle

TBD


### -param Mapping [in, out]

Pointer to a structure of type <a href="..\hbaapi\ns-hbaapi-hba_fcptargetmapping.md">HBA_FCPTargetMapping</a> that contains an array of bindings between operating system and FCP identifiers for a set of target devices. These mappings are maintained by the HBA referenced by <i>HbaHandle</i>. On input, the <b>NumberOfEntries</b> member of HBA_FCPTargetMapping should contain a number of mappings that fit in the output buffer. On output, the <b>NumberOfEntries</b> contains the number of mappings requested, or the full set of mappings, whichever is smaller. The value in <b>NumberOfEntries</b> contains the number of mappings returned even when an error occurred due to insufficient buffer space. 


#### - HbaHandle [in]

Contains a value returned by the routine <a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a> that identifies the HBA to query for the target mappings. The HBA returns mappings for the targets that it can enumerate. 


## -returns



The <b>HBA_GetFcpTargetMapping</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, <b>HBA_GetFcpTargetMapping</b> returns one of the following qualifiers.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_OK</b></dt>
</dl>
</td>
<td width="60%">
Returned if all the mapping entries were retrieved. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR_MORE_DATA</b></dt>
</dl>
</td>
<td width="60%">
Returned if there was insufficient buffer space to retrieve all of the target mappings. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR</b></dt>
</dl>
</td>
<td width="60%">
Returned if an unspecified error occurred that prevented the retrieval of the target mappings. 

</td>
</tr>
</table>
 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>



<a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a>



<a href="..\hbaapi\ns-hbaapi-hba_fcptargetmapping.md">HBA_FCPTargetMapping</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_GetFcpTargetMapping routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

