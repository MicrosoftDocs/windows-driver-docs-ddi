---
UID: NS:1394._GET_LOCAL_HOST_INFO5
title: "_GET_LOCAL_HOST_INFO5" (1394.h)
description: The GET_LOCAL_HOST_INFO5 structure contains the data returned by a REQUEST_GET_LOCAL_HOST_INFO request using u.GetLocalHostInformation.nLevel = GET_HOST_CONFIG_ROM.
old-location: ieee\get_local_host_info5.htm
tech.root: IEEE
ms.assetid: a0cdf40e-627e-4d39-9c7b-6defcc2f29c3
ms.date: 02/15/2018
ms.keywords: "*PGET_LOCAL_HOST_INFO5, 1394/GET_LOCAL_HOST_INFO5, 1394/PGET_LOCAL_HOST_INFO5, 1394stct_7be8f02e-9734-40ae-9337-91d9026ec65d.xml, GET_LOCAL_HOST_INFO5, GET_LOCAL_HOST_INFO5 structure [Buses], IEEE.get_local_host_info5, PGET_LOCAL_HOST_INFO5, PGET_LOCAL_HOST_INFO5 structure pointer [Buses], _GET_LOCAL_HOST_INFO5"
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
-	GET_LOCAL_HOST_INFO5
product:
- Windows
targetos: Windows
req.typenames: GET_LOCAL_HOST_INFO5, *PGET_LOCAL_HOST_INFO5
---

# _GET_LOCAL_HOST_INFO5 structure


## -description


The GET_LOCAL_HOST_INFO5 structure contains the data returned by a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537644">REQUEST_GET_LOCAL_HOST_INFO</a> request using <b>u.GetLocalHostInformation.nLevel</b> = GET_HOST_CONFIG_ROM.


## -struct-fields




### -field ConfigRom

Pointer to the beginning of the buffer to be filled with the local host's configuration ROM.


### -field ConfigRomLength

Specifies the length of the buffer pointed to by <b>ConfigRom</b>.


## -remarks



When submitted in a REQUEST_GET_LOCAL_HOST_INFO request, if the <b>ConfigRomLength</b> is smaller than the size of the Configuration ROM, a status code of STATUS_INVALID_BUFFER_SIZE is returned. In this case, the correct buffer size is filled in the <b>ConfigRomLength</b> member.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537644">REQUEST_GET_LOCAL_HOST_INFO</a>
 

 

