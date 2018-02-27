---
UID: NS:iscsiop._GetPresharedKeyForId_IN
title: "_GetPresharedKeyForId_IN"
author: windows-driver-content
description: The GetPresharedKeyForId_IN structure holds the input data for the GetPresharedKeyForId method.
old-location: storage\getpresharedkeyforid_in.htm
old-project: storage
ms.assetid: 4b3d3c5d-c34c-4ed8-bf62-1d885442ee1e
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PGetPresharedKeyForId_IN, GetPresharedKeyForId_IN, GetPresharedKeyForId_IN structure [Storage Devices], PGetPresharedKeyForId_IN, PGetPresharedKeyForId_IN structure pointer [Storage Devices], _GetPresharedKeyForId_IN, iscsiop/GetPresharedKeyForId_IN, iscsiop/PGetPresharedKeyForId_IN, storage.getpresharedkeyforid_in, structs-iSCSI_2bdada81-7b98-40cd-bc44-e23e53118c60.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iscsiop.h
req.include-header: Iscsiop.h
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
-	iscsiop.h
apiname:
-	GetPresharedKeyForId_IN
product: Windows
targetos: Windows
req.typenames: GetPresharedKeyForId_IN, *PGetPresharedKeyForId_IN
---

# _GetPresharedKeyForId_IN structure


## -description


The GetPresharedKeyForId_IN structure holds the input data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554970">GetPresharedKeyForId</a> method. This method is required if the initiator supports Internet Key Exchange (IKE). It can help to determine whether IKE identification payload is configured with a preshared key.


## -syntax


````
typedef struct _GetPresharedKeyForId_IN {
  ULONG PortNumber;
  UCHAR IdType;
  ULONG IdSize;
  UCHAR Id[1];
} GetPresharedKeyForId_IN, *PGetPresharedKeyForId_IN;
````


## -struct-fields




### -field PortNumber

The number of the port that the connection was made through. A value of -1 indicates that the connection can be made through any available port.


### -field IdType

The type of identifier that the initiator puts in the Internet Key Exchange (IKE) identification payload to identify itself to the target. 

<table>
<tr>
<th>Identification payload type</th>
<th>Meaning</th>
</tr>
<tr>
<td>
ID_IPV4_ADDR

</td>
<td>
The initiator identifies itself to the target during the key exchange with a single 4-byte version 4 IP address.

</td>
</tr>
<tr>
<td>
ID_FQDN

</td>
<td>
The initiator identifies itself to the target during the key exchange with a fully qualified domain name string (for example, "website.com"). 

</td>
</tr>
<tr>
<td>
ID_USER_FQDN

</td>
<td>
The initiator identifies itself to the target during the key exchange with a fully qualified user name string (for example, "someone@example.com"). 

</td>
</tr>
<tr>
<td>
ID_IPV6_ADDR

</td>
<td>
The initiator identifies itself to the target during the key exchange with a single 16-byte version 6 IP address.

</td>
</tr>
</table>
 


### -field IdSize

The size, in bytes, of the identifier in <b>Id</b><i>.</i>


### -field Id

The identifier that the initiator uses to identify itself to the target during key exchange. 


## -remarks



You must implement this method if the initiator supports IKE.




## -see-also

<a href="..\iscsiop\ns-iscsiop-_getpresharedkeyforid_out.md">GetPresharedKeyForId_OUT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563135">MSiSCSI_SecurityConfigOperations WMI Class</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554970">GetPresharedKeyForId</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20GetPresharedKeyForId_IN structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

