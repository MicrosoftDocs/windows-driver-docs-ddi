---
UID: NE:fwpsk.FWPS_FIELDS_ALE_CONNECT_REDIRECT_V4_
title: FWPS_FIELDS_ALE_CONNECT_REDIRECT_V4_
author: windows-driver-content
description: The FWPS_FIELDS_ALE_CONNECT_REDIRECT_V4 enumeration type specifies the data field identifiers for the FWPS_LAYER_ALE_CONNECT_REDIRECT_V4 run-time filtering layer.
old-location: netvista\fwps_fields_ale_connect_redirect_v4.htm
old-project: netvista
ms.assetid: df9b014f-2c47-4eed-af81-9cbe0f7a652d
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: wfp_ref_5_const_3_data_fields_f9393198-b18c-41f3-9a21-d9156f377121.xml, fwpsk/FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_ALE_APP_ID, fwpsk/FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_MAX, FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_ALE_ORIGINAL_APP_ID, fwpsk/FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_IP_REMOTE_ADDRESS, fwpsk/FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_IP_LOCAL_ADDRESS_TYPE, FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_ALE_APP_ID, FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_IP_PROTOCOL, fwpsk/FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_IP_LOCAL_ADDRESS, fwpsk/FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_FLAGS, fwpsk/FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_ALE_PACKAGE_ID, FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_MAX, FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_IP_REMOTE_ADDRESS, fwpsk/FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_ALE_ORIGINAL_APP_ID, FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_ALE_USER_ID, fwpsk/FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_ALE_USER_ID, FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_IP_DESTINATION_ADDRESS_TYPE, fwpsk/FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_IP_DESTINATION_ADDRESS_TYPE, fwpsk/FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_IP_REMOTE_PORT, FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_FLAGS, FWPS_FIELDS_ALE_CONNECT_REDIRECT_V4_, fwpsk/FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_IP_LOCAL_PORT, FWPS_FIELDS_ALE_CONNECT_REDIRECT_V4 enumeration [Network Drivers Starting with Windows Vista], FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_IP_LOCAL_PORT, FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_IP_LOCAL_ADDRESS, FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_ALE_PACKAGE_ID, FWPS_FIELDS_ALE_CONNECT_REDIRECT_V4, netvista.fwps_fields_ale_connect_redirect_v4, fwpsk/FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_IP_PROTOCOL, fwpsk/FWPS_FIELDS_ALE_CONNECT_REDIRECT_V4, FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_IP_REMOTE_PORT, FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_IP_LOCAL_ADDRESS_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Unless otherwise noted, supported starting with Windows 7.
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	fwpsk.h
apiname:
-	FWPS_FIELDS_ALE_CONNECT_REDIRECT_V4
product: Windows
targetos: Windows
req.typenames: FWPS_FIELDS_ALE_CONNECT_REDIRECT_V4
---

# FWPS_FIELDS_ALE_CONNECT_REDIRECT_V4_ enumeration


## -description


The FWPS_FIELDS_ALE_CONNECT_REDIRECT_V4 enumeration type specifies the data field identifiers for the
  FWPS_LAYER_ALE_CONNECT_REDIRECT_V4 
  <a href="https://msdn.microsoft.com/en-us/library/windows/desktop/aa366492">run-time filtering layer</a>.


## -syntax


````
typedef enum FWPS_FIELDS_ALE_CONNECT_REDIRECT_V4_ { 
  FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_ALE_APP_ID,
  FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_ALE_USER_ID,
  FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_IP_LOCAL_ADDRESS,
  FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_IP_LOCAL_ADDRESS_TYPE,
  FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_IP_LOCAL_PORT,
  FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_IP_PROTOCOL,
  FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_IP_REMOTE_ADDRESS,
  FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_IP_DESTINATION_ADDRESS_TYPE,
  FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_IP_REMOTE_PORT,
  FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_FLAGS,
#if (NTDDI_VERSION >= NTDDI_WIN8)
  FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_ALE_ORIGINAL_APP_ID,
  FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_ALE_PACKAGE_ID,
#endif 
  FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_MAX
} FWPS_FIELDS_ALE_CONNECT_REDIRECT_V4;
````


## -enum-fields




#### - FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_ALE_APP_ID

The full path of the application.


#### - FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_ALE_USER_ID

The identifier of the local user.


#### - FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_IP_LOCAL_ADDRESS

The local IP address.


#### - FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_IP_LOCAL_ADDRESS_TYPE

The local IP address type. The possible values are defined by the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568757">NL_ADDRESS_TYPE</a> enumeration.


#### - FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_IP_LOCAL_PORT

The local transport protocol port number.


#### - FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_IP_PROTOCOL

The IP protocol number, as specified in RFC 1700.


#### - FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_IP_REMOTE_ADDRESS

The remote IP address.


#### - FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_IP_DESTINATION_ADDRESS_TYPE

The destination IP address type. The possible values are defined by the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568757">NL_ADDRESS_TYPE</a> enumeration.


#### - FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_IP_REMOTE_PORT

The remote transport protocol port number.


#### - FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_FLAGS

A bitwise OR of a combination of filtering condition flags. For information about the possible
     flags, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff549942">Filtering Condition Flags</a>.


#### - FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_ALE_ORIGINAL_APP_ID

The full path of the original application for proxy connections. If the application has not been proxied, this path is identical to the xxx_ALE_APP_ID.
<div class="alert"><b>Note</b>  Supported starting with Windows 8.</div><div> </div>

#### - FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_ALE_PACKAGE_ID

The package identifier is a security identifier (SID) that identifies the associated AppContainer process. For more information about the SID structure, see the description for the SID structure in the Microsoft Windows SDK documentation.
<div class="alert"><b>Note</b>  Supported starting with Windows 8.</div><div> </div>

### -field FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_ALE_SECURITY_ATTRIBUTE_FQBN_VALUE



### -field FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_COMPARTMENT_ID



#### - FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_MAX

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.


## -remarks


The following macros in 
    <i>Fwpsk.h</i> are defined with FWPS_FIELDS_ALE_CONNECT_REDIRECT_V4 enumeration
    values:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
#define FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_ICMP_TYPE \
        FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_IP_LOCAL_PORT

#define FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_ICMP_CODE \
        FWPS_FIELD_ALE_CONNECT_REDIRECT_V4_IP_REMOTE_PORT
</pre>
</td>
</tr>
</table></span></div>These macros are used to access the following IPV4 data fields:





## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff568757">NL_ADDRESS_TYPE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FWPS_FIELDS_ALE_CONNECT_REDIRECT_V4 enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

