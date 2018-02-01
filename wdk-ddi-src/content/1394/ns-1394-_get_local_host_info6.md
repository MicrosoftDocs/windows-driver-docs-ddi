---
UID: NS:1394._GET_LOCAL_HOST_INFO6
title: "_GET_LOCAL_HOST_INFO6"
author: windows-driver-content
description: The GET_LOCAL_HOST_INFO6 structure contains the data returned by a REQUEST_GET_LOCAL_HOST_INFO request using u.GetLocalHostInformation.nLevel = GET_HOST_CSR_CONTENTS.
old-location: ieee\get_local_host_info6.htm
old-project: IEEE
ms.assetid: d5da15b9-a020-42bf-8876-cec9edf3119f
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: "*PGET_LOCAL_HOST_INFO6, GET_LOCAL_HOST_INFO6 structure [Buses], GET_LOCAL_HOST_INFO6, _GET_LOCAL_HOST_INFO6, 1394/GET_LOCAL_HOST_INFO6, IEEE.get_local_host_info6, PGET_LOCAL_HOST_INFO6, 1394stct_90799b58-816d-4624-a194-6b42d64b903c.xml, 1394/PGET_LOCAL_HOST_INFO6, PGET_LOCAL_HOST_INFO6 structure pointer [Buses]"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	1394.h
apiname:
-	GET_LOCAL_HOST_INFO6
product: Windows
targetos: Windows
req.typenames: "*PGET_LOCAL_HOST_INFO6, GET_LOCAL_HOST_INFO6"
---

# _GET_LOCAL_HOST_INFO6 structure


## -description


The GET_LOCAL_HOST_INFO6 structure contains the data returned by a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537644">REQUEST_GET_LOCAL_HOST_INFO</a> request using <b>u.GetLocalHostInformation.nLevel</b> = GET_HOST_CSR_CONTENTS.


## -syntax


````
typedef struct _GET_LOCAL_HOST_INFO6 {
  ADDRESS_OFFSET CsrBaseAddress;
  ULONG          CsrDataLength;
  PVOID          CsrDataBuffer;
} GET_LOCAL_HOST_INFO6, *PGET_LOCAL_HOST_INFO6;
````


## -struct-fields




### -field CsrBaseAddress

Specifies the base address to examine in the CSR. <b>CsrBaseAddress.Off_High</b> must be INITIAL_REGISTER_SPACE_HI. The possible values of <b>CsrBaseAddress.Off_Low</b> are as follows.
<table>
<tr>
<th>CsrBaseAddress.Off_Low</th>
<th>Type of Data</th>
</tr>
<tr>
<td>
SPEED_MAP_LOCATION

</td>
<td>
The current speed map. The bus driver converts this from big-endian to machine-native format before it returns the data.<div class="alert"><b>Note</b>  The new 1394 bus driver provided with Windows 7 does not support the SPEED_MAP_LOCATION flag in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537644">REQUEST_GET_LOCAL_HOST_INFO</a> request. The speed map is obsolete in the IEEE-1394a specification.</div>
<div> </div>


</td>
</tr>
<tr>
<td>
TOPOLOGY_MAP_LOCATION

</td>
<td>
The current topology map. The bus driver converts this from big-endian to machine-native format before it returns the data.

</td>
</tr>
</table> 


### -field CsrDataLength

Specifies the length in bytes of the buffer that <b>CsrDataBuffer</b> points to.


### -field CsrDataBuffer

Pointer to the buffer where the bus driver returns the requested CSR data.


## -remarks


When submitted in a REQUEST_GET_LOCAL_HOST_INFO request, if the <b>CsrDataLength</b> is smaller than the size of the requested data, STATUS_INVALID_BUFFER_SIZE is returned. In this case, the correct buffer size is filled in the <b>CsrDataLength</b> member.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537644">REQUEST_GET_LOCAL_HOST_INFO</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537147">GET_LOCAL_HOST_INFO2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20GET_LOCAL_HOST_INFO6 structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

