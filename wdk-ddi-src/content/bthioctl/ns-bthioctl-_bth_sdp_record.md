---
UID: NS:bthioctl._BTH_SDP_RECORD
title: "_BTH_SDP_RECORD"
author: windows-driver-content
description: The BTH_SDP_RECORD structure contains information about an SDP record that is to be added to the local SDP server.
old-location: bltooth\bth_sdp_record.htm
old-project: bltooth
ms.assetid: 29aeb49a-1647-46ee-a88e-f088f8a2548f
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PBTH_SDP_RECORD, BTH_SDP_RECORD, BTH_SDP_RECORD structure [Bluetooth Devices], PBTH_SDP_RECORD, PBTH_SDP_RECORD structure pointer [Bluetooth Devices], _BTH_SDP_RECORD, bltooth.bth_sdp_record, bth_structs_e77453a7-05d1-403d-9552-972368d7a76c.xml, bthioctl/BTH_SDP_RECORD, bthioctl/PBTH_SDP_RECORD"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bthioctl.h
req.include-header: Bthioctl.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
req.irql: "<= PASSIVE_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	bthioctl.h
apiname:
-	BTH_SDP_RECORD
product: Windows
targetos: Windows
req.typenames: BTH_SDP_RECORD, *PBTH_SDP_RECORD
---

# _BTH_SDP_RECORD structure


## -description


The BTH_SDP_RECORD structure contains information about an SDP record that is to be added to the
  local SDP server.


## -syntax


````
typedef struct _BTH_SDP_RECORD {
  ULONG fSecurity;
  ULONG fOptions;
  ULONG fCodService;
  ULONG recordLength;
  UCHAR record[1];
} BTH_SDP_RECORD, *PBTH_SDP_RECORD;
````


## -struct-fields




### -field fSecurity

A combination of flags that specifies the security attributes of the SDP record. Valid flag values
     are listed in the following table.
     

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
SERVICE_SECURITY_AUTHENTICATE

</td>
<td>
Only authenticated clients can access this record.

</td>
</tr>
<tr>
<td>
SERVICE_SECURITY_AUTHORIZE

</td>
<td>
Only authorized clients can access this record.

</td>
</tr>
<tr>
<td>
SERVICE_SECURITY_ENCRYPT_OPTIONAL

</td>
<td>
Encryption is optional to access this record.

</td>
</tr>
<tr>
<td>
SERVICE_SECURITY_ENCRYPT_REQUIRED

</td>
<td>
Encryption is required to access this record.

</td>
</tr>
<tr>
<td>
SERVICE_SECURITY_NONE

</td>
<td>
No security is required to access this record.

</td>
</tr>
</table>
 


### -field fOptions

A combination of flags that specifies the publication options for the SDP record. Valid flag
     values are listed in the following table.
     

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
SERVICE_OPTION_DO_NOT_PUBLISH

</td>
<td>
The record should be entered into the local SDP server, but should not be published to remote
        systems.

</td>
</tr>
<tr>
<td>
SERVICE_OPTION_NO_PUBLIC_BROWSE

</td>
<td>
The record should be obtainable if specifically requested, but it should not be browseable using
        SDP browse groups.

</td>
</tr>
</table>
 


### -field fCodService



######  Possible values include:



#### COD_SERVICE_AUDIO



#### COD_SERVICE_CAPTURING



#### COD_SERVICE_INFORMATION



#### COD_SERVICE_LIMITED



#### COD_SERVICE_NETWORKING



#### COD_SERVICE_OBJECT_XFER



#### COD_SERVICE_POSITIONING



#### COD_SERVICE_RENDERING



#### COD_SERVICE_TELEPHONY


### -field recordLength

The size, in bytes, of the record.


### -field record


      The SDP record in its raw stream format. The first byte is defined in this structure, with the
      entire record following it.
     


## -remarks



This structure is passed as the input buffer and output buffer of 
    <a href="..\bthioctl\ni-bthioctl-ioctl_bth_sdp_submit_record_with_info.md">
    IOCTL_BTH_SDP_SUBMIT_RECORD_WITH_INFO</a>.




## -see-also

<a href="..\bthioctl\ni-bthioctl-ioctl_bth_sdp_submit_record_with_info.md">
   IOCTL_BTH_SDP_SUBMIT_RECORD_WITH_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20BTH_SDP_RECORD structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

