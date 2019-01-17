---
UID: NS:1394._GET_LOCAL_HOST_INFO1
title: "_GET_LOCAL_HOST_INFO1"
description: The GET_LOCAL_HOST_INFO1 structure contains the data returned by a REQUEST_GET_LOCAL_HOST_INFO request using u.GetLocalHostInformation.nLevel GET_HOST_UNIQUE_ID.
old-location: ieee\get_local_host_info1.htm
tech.root: IEEE
ms.assetid: 49ec5322-2caa-4e95-85d0-74b9137d9bcd
ms.date: 02/15/2018
ms.keywords: "*PGET_LOCAL_HOST_INFO1, 1394/GET_LOCAL_HOST_INFO1, 1394/PGET_LOCAL_HOST_INFO1, 1394stct_17301961-cba0-4966-851a-bd92fec75bc7.xml, GET_LOCAL_HOST_INFO1, GET_LOCAL_HOST_INFO1 structure [Buses], IEEE.get_local_host_info1, PGET_LOCAL_HOST_INFO1, PGET_LOCAL_HOST_INFO1 structure pointer [Buses], _GET_LOCAL_HOST_INFO1"
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
-	GET_LOCAL_HOST_INFO1
product:
- Windows
targetos: Windows
req.typenames: GET_LOCAL_HOST_INFO1, *PGET_LOCAL_HOST_INFO1
---

# _GET_LOCAL_HOST_INFO1 structure


## -description


The GET_LOCAL_HOST_INFO1 structure contains the data returned by a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537644">REQUEST_GET_LOCAL_HOST_INFO</a> request using <b>u.GetLocalHostInformation.nLevel</b> GET_HOST_UNIQUE_ID.


## -struct-fields




### -field UniqueId

The bus driver fills in this member with the IEEE 1394 globally unique device ID for the host controller.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537644">REQUEST_GET_LOCAL_HOST_INFO</a>
 

 

