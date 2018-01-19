---
UID: NF:hbaapi.HBA_GetFcpTargetMapping
title: HBA_GetFcpTargetMapping function
author: windows-driver-content
description: The HBA_GetFcpTargetMapping routine retrieves the mappings between operating system and fibre channel protocol (FCP) identifiers for a set of targets that the HBA can enumerate.
old-location: storage\hba_getfcptargetmapping.htm
old-project: storage
ms.assetid: d1064f97-e640-49b6-be8c-19662e5de9bb
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: HBA_GetFcpTargetMapping
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
req.alt-api: HBA_GetFcpTargetMapping
req.alt-loc: Hbaapi.dll
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

### -param HbaHandle [in]

Contains a value returned by the routine <a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a> that identifies the HBA to query for the target mappings. The HBA returns mappings for the targets that it can enumerate. 


### -param Mapping [in, out]

Pointer to a structure of type <a href="..\hbaapi\ns-hbaapi-hba_fcptargetmapping.md">HBA_FCPTargetMapping</a> that contains an array of bindings between operating system and FCP identifiers for a set of target devices. These mappings are maintained by the HBA referenced by <i>HbaHandle</i>. On input, the <b>NumberOfEntries</b> member of HBA_FCPTargetMapping should contain a number of mappings that fit in the output buffer. On output, the <b>NumberOfEntries</b> contains the number of mappings requested, or the full set of mappings, whichever is smaller. The value in <b>NumberOfEntries</b> contains the number of mappings returned even when an error occurred due to insufficient buffer space. 


## -returns
The <b>HBA_GetFcpTargetMapping</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, <b>HBA_GetFcpTargetMapping</b> returns one of the following qualifiers.
<dl>
<dt><b>HBA_STATUS_OK</b></dt>
</dl>Returned if all the mapping entries were retrieved. 
<dl>
<dt><b>HBA_STATUS_ERROR_MORE_DATA</b></dt>
</dl>Returned if there was insufficient buffer space to retrieve all of the target mappings. 
<dl>
<dt><b>HBA_STATUS_ERROR</b></dt>
</dl>Returned if an unspecified error occurred that prevented the retrieval of the target mappings. 

 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\hbaapi\ns-hbaapi-hba_fcptargetmapping.md">HBA_FCPTargetMapping</a>
</dt>
<dt>
<a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_GetFcpTargetMapping routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

