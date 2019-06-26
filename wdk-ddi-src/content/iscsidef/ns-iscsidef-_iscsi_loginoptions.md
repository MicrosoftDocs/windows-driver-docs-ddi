---
UID: NS:iscsidef._ISCSI_LoginOptions
title: _ISCSI_LoginOptions (iscsidef.h)
description: The ISCSI_LoginOptions structure defines the characteristics of a logon session. The LoginToTarget_IN routines use these defined characteristics while it logs into an iSCSI target.
old-location: storage\iscsi_loginoptions.htm
tech.root: storage
ms.assetid: 2440999a-e10c-4a27-b076-a0b640c2ca7f
ms.date: 03/29/2018
ms.keywords: "*PISCSI_LoginOptions, ISCSI_LoginOptions, ISCSI_LoginOptions structure [Storage Devices], PISCSI_LoginOptions, PISCSI_LoginOptions structure pointer [Storage Devices], _ISCSI_LoginOptions, iscsidef/ISCSI_LoginOptions, iscsidef/PISCSI_LoginOptions, storage.iscsi_loginoptions, structs-iSCSI_d6ba6d7e-95c3-42a4-bed9-c038c1702d59.xml"
ms.topic: struct
req.header: iscsidef.h
req.include-header: Iscsidef.h
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
- iscsidef.h
api_name:
- ISCSI_LoginOptions
product:
- Windows
targetos: Windows
req.typenames: ISCSI_LoginOptions, *PISCSI_LoginOptions
---

# _ISCSI_LoginOptions structure


## -description


The ISCSI_LoginOptions structure defines the characteristics of a logon session. The LoginToTarget_IN routines use these defined characteristics while it logs into an iSCSI target.


## -struct-fields




### -field InformationSpecified

A bitmap that indicates which members of the ISCSI_LoginOptions structure contain valid data. The following table describes the possible values: 

<table>
<tr>
<th>Bit</th>
<th>Description</th>
</tr>
<tr>
<td>
ISCSI_LOGIN_OPTIONS_HEADER_DIGEST

</td>
<td>
The <b>HeaderDigest</b> member specifies the type of digest that is used to guarantee the integrity of header data. 

</td>
</tr>
<tr>
<td>
ISCSI_LOGIN_OPTIONS_DATA_DIGEST

</td>
<td>
The <b>DataDigest</b> member specifies the type of digest that is used to guarantee the integrity of header data.

</td>
</tr>
<tr>
<td>
ISCSI_LOGIN_OPTIONS_MAXIMUM_CONNECTIONS

</td>
<td>
The <b>MaximumConnections</b> member specifies the maximum number of connections that are allowed in the iSCSI session. 

</td>
</tr>
<tr>
<td>
ISCSI_LOGIN_OPTIONS_DEFAULT_TIME_2_WAIT

</td>
<td>
The <b>DefaultTime2Wait</b> member specifies the minimum time to wait, in seconds, before the initiator attempts to reconnect or reassign a connection that was dropped. 

</td>
</tr>
<tr>
<td>
ISCSI_LOGIN_OPTIONS_DEFAULT_TIME_2_RETAIN

</td>
<td>
The <b>DefaultTime2Retain</b> member specifies the maximum time that is allowed to reassign commands after the initial wait indicated in <b>DefaultTime2Wait</b>.

</td>
</tr>
<tr>
<td>
ISCSI_LOGIN_OPTIONS_AUTH_TYPE

</td>
<td>
The <b>AuthType</b> member specifies the type of authentication that establishes the logon session. 

</td>
</tr>
<tr>
<td>
ISCSI_LOGIN_OPTIONS_USERNAME

</td>
<td>
The username to be used during logon. 

</td>
</tr>
<tr>
<td>
ISCSI_LOGIN_OPTIONS_PASSWORD

</td>
<td>
The password to be used during logon. 

</td>
</tr>
</table>
 


### -field HeaderDigest

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/iscsidef/ne-iscsidef-iscsi_digest_types">ISCSI_DIGEST_TYPES</a> value that indicates the method that the initiator uses to verify the integrity of the header digest in a logon PDU.


### -field DataDigest

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/iscsidef/ne-iscsidef-iscsi_digest_types">ISCSI_DIGEST_TYPES</a> value that indicates the method that the initiator uses to verify the integrity of the data digest in a logon PDU.


### -field MaximumConnections

A value between 1 and 65535 that specifies the maximum number of connections to target devices that can be associated with a single logon session. A value of 0 indicates that there is no limit to the number of connections. 


### -field DefaultTime2Wait

The minimum time to wait, in seconds, before the initiator attempts to reconnect or reassign a connection (or task) that has been dropped after an unexpected connection termination or reset. The initiator and target negotiate to determine this value.


### -field DefaultTime2Retain

The maximum time, in seconds, to reassign a connection after the initial wait that is indicated in <b>DefaultTime2Wait</b> has elapsed. The initiator and target negotiate to determine this value.


### -field LoginFlags

A bitwise OR of logon flags that define certain characteristics of the logon session. The following table indicates the values that you can assign to this member.

<table>
<tr>
<th>Logon flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
ISCSI_LOGIN_FLAG_REQUIRE_IPSEC

</td>
<td>
The logon session must use the IPSec protocol.

</td>
</tr>
<tr>
<td>
ISCSI_LOGIN_FLAG_MULTIPATH_ENABLED

</td>
<td>
Multipathing software is installed, so the iSCSI initiator service allows multiple sessions to the same target.  

</td>
</tr>
<tr>
<td>
ISCSI_LOGIN_FLAG_RESERVED1

</td>
<td>
Microsoft internal use only.  

</td>
</tr>
<tr>
<td>
ISCSI_LOGIN_FLAG_ALLOW_PORTAL_HOPPING

</td>
<td>
If a target portal is not available for login, the initiator can "hop" through the list of target portals that it discovered and that can be used for login operations. That is, the initiator will continue to try the list of portals that are available until it finds one that can be used for login, so it can then log in to the available target portal.

</td>
</tr>
<tr>
<td>
ISCSI_LOGIN_FLAG_USE_RADIUS_RESPONSE

</td>
<td>
Use RADIUS to generate CHAP response.  

</td>
</tr>
<tr>
<td>
ISCSI_LOGIN_FLAG_USE_RAIDUS_VERIFICATION

</td>
<td>
Use RADIUS to verify CHAP response.  

</td>
</tr>
</table>
 


### -field AuthType

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/iscsidef/ne-iscsidef-iscsi_auth_types">ISCSI_AUTH_TYPES</a> value that indicates the authentication method that is used to establish a logon connection. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/iscsidef/ne-iscsidef-iscsi_auth_types">ISCSI_AUTH_TYPES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/iscsidef/ne-iscsidef-iscsi_digest_types">ISCSI_DIGEST_TYPES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/iscsi-loginoptions-wmi-class">ISCSI_LoginOptions WMI Class</a>
 

 

