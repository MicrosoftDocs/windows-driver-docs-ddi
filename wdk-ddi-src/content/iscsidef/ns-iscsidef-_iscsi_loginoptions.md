---
UID: NS:iscsidef._ISCSI_LoginOptions
title: "_ISCSI_LoginOptions"
author: windows-driver-content
description: The ISCSI_LoginOptions structure defines the characteristics of a logon session. The LoginToTarget_IN routines use these defined characteristics while it logs into an iSCSI target.
old-location: storage\iscsi_loginoptions.htm
old-project: storage
ms.assetid: 2440999a-e10c-4a27-b076-a0b640c2ca7f
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: PISCSI_LoginOptions structure pointer [Storage Devices], *PISCSI_LoginOptions, structs-iSCSI_d6ba6d7e-95c3-42a4-bed9-c038c1702d59.xml, iscsidef/PISCSI_LoginOptions, storage.iscsi_loginoptions, ISCSI_LoginOptions structure [Storage Devices], iscsidef/ISCSI_LoginOptions, _ISCSI_LoginOptions, PISCSI_LoginOptions, ISCSI_LoginOptions
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	iscsidef.h
apiname:
-	ISCSI_LoginOptions
product: Windows
targetos: Windows
req.typenames: "*PISCSI_LoginOptions, ISCSI_LoginOptions"
---

# _ISCSI_LoginOptions structure


## -description


The ISCSI_LoginOptions structure defines the characteristics of a logon session. The LoginToTarget_IN routines use these defined characteristics while it logs into an iSCSI target.


## -syntax


````
typedef struct _ISCSI_LoginOptions {
  ULONG InformationSpecified;
  ULONG HeaderDigest;
  ULONG DataDigest;
  ULONG MaximumConnections;
  ULONG DefaultTime2Wait;
  ULONG DefaultTime2Retain;
  ULONG LoginFlags;
  ULONG AuthType;
} ISCSI_LoginOptions, *PISCSI_LoginOptions;
````


## -struct-fields




#### - InformationSpecified

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


#### - HeaderDigest

A <a href="..\iscsidef\ne-iscsidef-piscsi_digest_types.md">ISCSI_DIGEST_TYPES</a> value that indicates the method that the initiator uses to verify the integrity of the header digest in a logon PDU.


#### - DataDigest

A <a href="..\iscsidef\ne-iscsidef-piscsi_digest_types.md">ISCSI_DIGEST_TYPES</a> value that indicates the method that the initiator uses to verify the integrity of the data digest in a logon PDU.


#### - MaximumConnections

A value between 1 and 65535 that specifies the maximum number of connections to target devices that can be associated with a single logon session. A value of 0 indicates that there is no limit to the number of connections. 


#### - DefaultTime2Wait

The minimum time to wait, in seconds, before the initiator attempts to reconnect or reassign a connection (or task) that has been dropped after an unexpected connection termination or reset. The initiator and target negotiate to determine this value.


#### - DefaultTime2Retain

The maximum time, in seconds, to reassign a connection after the initial wait that is indicated in <b>DefaultTime2Wait</b> has elapsed. The initiator and target negotiate to determine this value.


#### - LoginFlags

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


#### - AuthType

A <a href="..\iscsidef\ne-iscsidef-piscsi_auth_types.md">ISCSI_AUTH_TYPES</a> value that indicates the authentication method that is used to establish a logon connection. 


## -see-also

<a href="..\iscsidef\ne-iscsidef-piscsi_auth_types.md">ISCSI_AUTH_TYPES</a>

<a href="..\iscsidef\ne-iscsidef-piscsi_digest_types.md">ISCSI_DIGEST_TYPES</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561543">ISCSI_LoginOptions WMI Class</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ISCSI_LoginOptions structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

