---
UID: NS:1394._GET_LOCAL_HOST_INFO8
title: "_GET_LOCAL_HOST_INFO8"
author: windows-driver-content
description: The GET_LOCAL_HOST_INFO8 structure contains the data returned by a REQUEST_GET_LOCAL_HOST_INFO request with u.GetLocalHostInformation.nLevel set to GET_HOST_DDI_VERSION.
old-location: ieee\get_local_host_info8.htm
old-project: IEEE
ms.assetid: DA30F8BA-B920-458E-B7C7-8D7B7081507A
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IEEE.get_local_host_info8, 1394/PGET_LOCAL_HOST_INFO8, *PGET_LOCAL_HOST_INFO8, 1394/GET_LOCAL_HOST_INFO8, _GET_LOCAL_HOST_INFO8, GET_LOCAL_HOST_INFO8 structure [Buses], GET_LOCAL_HOST_INFO8, PGET_LOCAL_HOST_INFO8 structure pointer [Buses], PGET_LOCAL_HOST_INFO8
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 1394.h
req.include-header: 1394.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions.
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
-	GET_LOCAL_HOST_INFO8
product: Windows
targetos: Windows
req.typenames: "*PGET_LOCAL_HOST_INFO8, GET_LOCAL_HOST_INFO8"
---

# _GET_LOCAL_HOST_INFO8 structure


## -description


The <b>GET_LOCAL_HOST_INFO8</b> structure contains the data returned by a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537644">REQUEST_GET_LOCAL_HOST_INFO</a> request with <b>u.GetLocalHostInformation.nLevel</b> set to GET_HOST_DDI_VERSION.


## -syntax


````
typedef struct _GET_LOCAL_HOST_INFO8 {
  USHORT MajorVersion;
  USHORT MinorVersion;
} GET_LOCAL_HOST_INFO8, *PGET_LOCAL_HOST_INFO8;
````


## -struct-fields




### -field MajorVersion

The major version of the 1394 bus driver interface.


### -field MinorVersion

The minor version of the 1394 bus driver interface.


## -remarks


A client driver can determine whether the 1394 bus driver
loaded in the IEEE 1394 driver stack is the new 1394 bus driver or the legacy
1394 bus driver. A new <b>nLevel</b> value has been added
to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537644">REQUEST_GET_LOCAL_HOST_INFO</a> I/O
request to return the version of the DDIs that the 1394 bus driver supports.


To determine whether the 1394 bus driver is the new 1394 bus
driver or the legacy 1394 bus driver,
<ol>
<li>The client driver must send
the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537644">REQUEST_GET_LOCAL_HOST_INFO</a> request with <b>nLevel</b>
set to GET_HOST_DDI_VERSION. If the driver stack contains the new 1394 bus
driver, the request returns a status value of STATUS_SUCCESS. Otherwise, the
legacy 1394 bus driver returns a status value of
STATUS_INVALID_PARAMETER.

</li>
<li>The client driver must also provide a
pointer to a caller-allocated <b>GET_LOCAL_HOST_INFO8</b> structure in
<b>u.GetLocalHostInformation.Information</b>. Upon
successful completion, the new 1394 bus driver (1394ohci.sys bus driver)sets the <b>MajorVersion</b> and <b>MinorVersion</b> members as follows.<ul>
<li>BUS1394_DDI_MAJOR_VERSION: 	The major version of the 1394 bus driver interface.
</li>
<li>BUS1394_DDI_MINOR_VERSION:	The minor version of the 1394 bus driver interface.
</li>
</ul>
</li>
</ol>

