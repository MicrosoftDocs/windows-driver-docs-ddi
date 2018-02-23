---
UID: NS:1394._IRB_REQ_SET_LOCAL_HOST_PROPERTIES
title: "_IRB_REQ_SET_LOCAL_HOST_PROPERTIES"
author: windows-driver-content
description: This structure contains the fields required to carry out a SetLocalHostProperties request.
old-location: ieee\irb_req_set_local_host_properties.htm
old-project: IEEE
ms.assetid: 59C1BBEF-ECC8-4852-B2E2-75751B5B25B2
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IEEE.irb_req_set_local_host_properties, IRB_REQ_SET_LOCAL_HOST_PROPERTIES, IRB_REQ_SET_LOCAL_HOST_PROPERTIES structure [Buses], _IRB_REQ_SET_LOCAL_HOST_PROPERTIES, 1394/IRB_REQ_SET_LOCAL_HOST_PROPERTIES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 1394.h
req.include-header: 
req.target-type: Windows
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	1394.h
apiname:
-	IRB_REQ_SET_LOCAL_HOST_PROPERTIES
product: Windows
targetos: Windows
req.typenames: IRB_REQ_SET_LOCAL_HOST_PROPERTIES
---

# _IRB_REQ_SET_LOCAL_HOST_PROPERTIES structure


## -description


This structure contains the fields required to carry out a SetLocalHostProperties request.


## -syntax


````
typedef struct _IRB_REQ_SET_LOCAL_HOST_PROPERTIES {
  ULONG nLevel;
  PVOID Information;
} IRB_REQ_SET_LOCAL_HOST_PROPERTIES;
````


## -struct-fields




### -field nLevel

Specifies what level of information is desired from this call. The following flags are provided.  

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
SET_LOCAL_HOST_PROPERTIES_GAP_COUNT 

</td>
<td>
Sets a lower bound on the value the bus uses for its gap count. See the <i>IEEE 1394-1995 Specification</i> for a description of the gap count. 

</td>
</tr>
<tr>
<td>
SET_LOCAL_HOST_PROPERTIES_MODIFY_CROM

</td>
<td>
Used to add or remove unit directories. This request cannot be used to modify instance directories or root keys in the configuration ROM. 

</td>
</tr>
</table>
 


### -field Information

Points to an information block to be filled in. The information returned depends on the value in <b>u.SetLocalHostProperties.nLevel</b>. Each block has its own particular structure.

<table>
<tr>
<th>Flag</th>
<th>Structure</th>
</tr>
<tr>
<td>
SET_LOCAL_HOST_PROPERTIES_GAP_COUNT 

</td>
<td>
SET_LOCAL_HOST_PROPS2

</td>
</tr>
<tr>
<td>
SET_LOCAL_HOST_PROPERTIES_MODIFY_CROM

</td>
<td>
SET_LOCAL_HOST_PROPS3

</td>
</tr>
</table>
 

