---
UID: NS:wwan._WWAN_SMS_SEND_PDU
title: "_WWAN_SMS_SEND_PDU"
author: windows-driver-content
description: The WWAN_SMS_SEND_PDU structure represents a PDU-style SMS message.
old-location: netvista\wwan_sms_send_pdu.htm
old-project: netvista
ms.assetid: 94d19d5b-8fa5-437d-9359-e35ef103f380
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PWWAN_SMS_SEND_PDU, PWWAN_SMS_SEND_PDU, PWWAN_SMS_SEND_PDU structure pointer [Network Drivers Starting with Windows Vista], WWAN_SMS_SEND_PDU, WWAN_SMS_SEND_PDU structure [Network Drivers Starting with Windows Vista], WwanRef_5994a030-78ea-42c2-913a-1b2a9fcc2ea4.xml, _WWAN_SMS_SEND_PDU, netvista.wwan_sms_send_pdu, wwan/PWWAN_SMS_SEND_PDU, wwan/WWAN_SMS_SEND_PDU"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
-	wwan.h
api_name:
-	WWAN_SMS_SEND_PDU
product: Windows
targetos: Windows
req.typenames: WWAN_SMS_SEND_PDU, *PWWAN_SMS_SEND_PDU
req.product: Windows 10 or later.
---

# _WWAN_SMS_SEND_PDU structure


## -description


The WWAN_SMS_SEND_PDU structure represents a PDU-style SMS message.


## -struct-fields




### -field Size

For GSM-based devices that support PDU-style SMS messages, the size, in bytes, of the message
     before conversion to hexadecimal.
     

For CDMA-based devices that support sending SMS messages in binary format, the size, in bytes, of the
     message in 
     <b>PduData</b> .

The following table lists the different values for the 
     <b>SmsFormat</b> member of the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571250">WWAN_SMS_SEND</a> structure and their
     corresponding range that is allowed in this member.

<table>
<tr>
<th>SmsFormat</th>
<th>Size</th>
</tr>
<tr>
<td>
WwanSmsFormatPdu

</td>
<td>
1 to WWAN_SMS_RAW_PDU_LEN

</td>
</tr>
<tr>
<td>
WwanSmsFormatCdma

</td>
<td>
1 to WWAN_SMS_CDMA_MAX_MSG_LEN

</td>
</tr>
</table>
 

<div class="alert"><b>Note</b>  For GSM-based devices, if 
     <b>ElementType</b> is set to 
     <b>WwanStructSmsPdu</b>, this member describes the size, in bytes, of 
     <b>PduData</b> excluding the Service Center address. The first byte of 
     <b>PduData</b> represents the size of the Service Center address that the miniport driver must add when
     it calculates the exact size of the 
     <b>PduData</b> buffer.
     <p class="note">For example:

<p class="note">If 
     <b>PduData</b> [0] = 0, then the size of 
     <b>PduData</b> is 
     <b>Size</b> + 1.

<p class="note">If 
     <b>PduData</b> [0] != 0, then the size of 
     <b>PduData</b> is 
     <b>Size</b> + 
     <b>PduData</b> [0].

</div>
<div> </div>

### -field PduData

A NULL-terminated string that represents the content of the record.
     

For GSM-based devices, the contents are coded in a hexadecimal string format (according to the 3GPP
     TS 27.005 and 3GPP TS 23.040 standards) that represents the SMS text message.

For CDMA-based devices that support sending SMS messages in binary format (that is, miniport drivers
     that return WWAN_SMS_CAPS_PDU_SEND in the 
     <b>WwanSmsCaps</b> member of 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571204">WWAN_DEVICE_CAPS</a>), 
     <b>PduData</b> contains the SMS message as a byte array, as defined in section 3.4.2.1 SMS Point-to-Point
     Message in the 3GPP2 specification C.S0015-A "Short Message Service (SMS) for Wideband Spread Spectrum
     Systems". SMS will only support Wireless Messaging Teleservice (WMT) format. Miniport drivers should
     typecast this information to BYTE[] for CDMA-based devices. It is not coded in hexadecimal string
     format.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff571250">WWAN_SMS_SEND</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_SMS_SEND_PDU structure%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

