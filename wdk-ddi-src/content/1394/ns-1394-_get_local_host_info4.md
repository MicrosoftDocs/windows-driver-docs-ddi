---
UID: NS:1394._GET_LOCAL_HOST_INFO4
title: "_GET_LOCAL_HOST_INFO4"
author: windows-driver-content
description: The GET_LOCAL_HOST_INFO4 structure contains the data returned by a REQUEST_GET_LOCAL_HOST_INFO request using u.GetLocalHostInformation.nLevel = GET_PHYS_ADDR_ROUTINE.
old-location: ieee\get_local_host_info4.htm
old-project: IEEE
ms.assetid: 72bc1d4b-cc68-4ea8-9431-c85cbcf135d8
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PGET_LOCAL_HOST_INFO4, 1394/GET_LOCAL_HOST_INFO4, 1394/PGET_LOCAL_HOST_INFO4, 1394stct_c06286e2-308d-4534-9a1b-14d3a04b5f86.xml, GET_LOCAL_HOST_INFO4, GET_LOCAL_HOST_INFO4 structure [Buses], IEEE.get_local_host_info4, PGET_LOCAL_HOST_INFO4, PGET_LOCAL_HOST_INFO4 structure pointer [Buses], _GET_LOCAL_HOST_INFO4"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 1394.h
req.include-header: 1394.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	1394.h
api_name:
-	GET_LOCAL_HOST_INFO4
product: Windows
targetos: Windows
req.typenames: GET_LOCAL_HOST_INFO4, *PGET_LOCAL_HOST_INFO4
---

# _GET_LOCAL_HOST_INFO4 structure


## -description


The GET_LOCAL_HOST_INFO4 structure contains the data returned by a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537644">REQUEST_GET_LOCAL_HOST_INFO</a> request using <b>u.GetLocalHostInformation.nLevel</b> = GET_PHYS_ADDR_ROUTINE.


## -struct-fields




### -field PhysAddrMappingRoutine

Pointer to the physical address mapping routine, which is of type: 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
PhysAddrMappingRoutine ( 
    IN PVOID Context,
    IN OUT PIRB Irb
);</pre>
</td>
</tr>
</table></span></div>
The physical mapping routine is invoked on an <a href="https://msdn.microsoft.com/library/windows/hardware/ff537632">REQUEST_ALLOCATE_ADDRESS_RANGE</a> IRB. It fills in the <b>u.AllocateAddressRange.pAddressRange</b> member with the physical addresses that the <b>u.AllocateAddressRange.Mdl</b> member of the IRB are mapped to. The proper value for the <i>Context</i> parameter is the <b>Context</b> member below.


### -field Context

Specifies the argument that should be passed as the Context argument of the physical address mapping routine.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537632">REQUEST_ALLOCATE_ADDRESS_RANGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537644">REQUEST_GET_LOCAL_HOST_INFO</a>
 

 

