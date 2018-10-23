---
UID: NF:hbaapi.HBA_GetFcpTargetMapping
title: HBA_GetFcpTargetMapping function
author: windows-driver-content
description: The HBA_GetFcpTargetMapping routine retrieves the mappings between operating system and fibre channel protocol (FCP) identifiers for a set of targets that the HBA can enumerate.
old-location: storage\hba_getfcptargetmapping.htm
tech.root: storage
ms.assetid: d1064f97-e640-49b6-be8c-19662e5de9bb
ms.date: 03/29/2018
ms.keywords: HBA_GetFcpTargetMapping, HBA_GetFcpTargetMapping routine [Storage Devices], fibreHBA_rtns_352928a8-39d5-4989-8156-0b1025b59350.xml, hbaapi/HBA_GetFcpTargetMapping, storage.hba_getfcptargetmapping
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Hbaapi.dll
api_name:
-	HBA_GetFcpTargetMapping
product:
- Windows
targetos: Windows
req.typenames: 
---

# HBA_GetFcpTargetMapping function


## -description


The <b>HBA_GetFcpTargetMapping</b> routine retrieves the mappings between operating system and fibre channel protocol (FCP) identifiers for a set of targets that the HBA can enumerate.


## -parameters




### -param Handle

<p>Contains a value returned by the routine <a href="https://msdn.microsoft.com/library/Ff557097(v=VS.85).aspx"><b>HBA_OpenAdapter</b></a> that identifies the HBA to query for the target mappings. The HBA returns mappings for the targets that it can enumerate. </p>


### -param Mapping [in, out]

Pointer to a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff556069">HBA_FCPTargetMapping</a> that contains an array of bindings between operating system and FCP identifiers for a set of target devices. These mappings are maintained by the HBA referenced by <i>HbaHandle</i>. On input, the <b>NumberOfEntries</b> member of HBA_FCPTargetMapping should contain a number of mappings that fit in the output buffer. On output, the <b>NumberOfEntries</b> contains the number of mappings requested, or the full set of mappings, whichever is smaller. The value in <b>NumberOfEntries</b> contains the number of mappings returned even when an error occurred due to insufficient buffer space. 


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556069">HBA_FCPTargetMapping</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557097">HBA_OpenAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>
 

 

