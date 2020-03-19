---
UID: NS:iscsiop._SetPresharedKeyForId_IN
title: _SetPresharedKeyForId_IN (iscsiop.h)
description: The SetPresharedKeyForId_IN structure holds the input data for the SetPresharedKeyForId method.
old-location: storage\setpresharedkeyforid_in.htm
tech.root: storage
ms.assetid: f941bc28-f906-4399-be54-09e2bc12e443
ms.date: 03/29/2018
keywords: ["_SetPresharedKeyForId_IN structure"]
ms.keywords: "*PSetPresharedKeyForId_IN, PSetPresharedKeyForId_IN, PSetPresharedKeyForId_IN structure pointer [Storage Devices], SetPresharedKeyForId_IN, SetPresharedKeyForId_IN structure [Storage Devices], _SetPresharedKeyForId_IN, iscsiop/PSetPresharedKeyForId_IN, iscsiop/SetPresharedKeyForId_IN, storage.setpresharedkeyforid_in, structs-iSCSI_610ad061-d9c5-4557-88c0-e7d9a20236a2.xml"
f1_keywords:
 - "iscsiop/SetPresharedKeyForId_IN"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- iscsiop.h
api_name:
- SetPresharedKeyForId_IN
product:
- Windows
targetos: Windows
req.typenames: SetPresharedKeyForId_IN, *PSetPresharedKeyForId_IN
---

# _SetPresharedKeyForId_IN structure


## -description


The SetPresharedKeyForId_IN structure holds the input data for the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/setpresharedkeyforid">SetPresharedKeyForId</a> method.


## -struct-fields




### -field PortNumber

The number of the port that the initiator uses the preshared key with. A value of 0xffffffff indicates all ports.


### -field SecurityFlags

A bitwise OR of flags that indicate the security requirements of a target.  For a list of possible values for this member, see <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/security-flag-qualifiers">SECURITY_FLAG_QUALIFIERS</a>.


### -field IdType

The type of identifier to associate with the preshared key. The initiator puts this identifier (ID) in the Internet key exchange (IKE) identification payload to identify itself to the target. The following table describes the possible identification payload types.

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
The initiator identifies itself to the target during the key exchange with a fully qualified user name string (for example, "sample@example.com"). 

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


### -field KeySize

The size, in bytes, of the key in <b>Key</b><i>.</i>


### -field Id

The ID to associate with the key. The initiator uses this ID to identify itself to the target during key exchange.


## -remarks



You must implement this method.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/security-flag-qualifiers">SECURITY_FLAG_QUALIFIERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/setpresharedkeyforid">SetPresharedKeyForId</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsiop/ns-iscsiop-_setpresharedkeyforid_out">SetPresharedKeyForId_OUT</a>
 

 

