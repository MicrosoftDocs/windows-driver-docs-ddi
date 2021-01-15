---
UID: NS:wwan._WWAN_SMS_SEND_PDU
title: _WWAN_SMS_SEND_PDU (wwan.h)
description: The WWAN_SMS_SEND_PDU structure represents a PDU-style SMS message.
old-location: netvista\wwan_sms_send_pdu.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["WWAN_SMS_SEND_PDU structure"]
ms.keywords: "*PWWAN_SMS_SEND_PDU, PWWAN_SMS_SEND_PDU, PWWAN_SMS_SEND_PDU structure pointer [Network Drivers Starting with Windows Vista], WWAN_SMS_SEND_PDU, WWAN_SMS_SEND_PDU structure [Network Drivers Starting with Windows Vista], WwanRef_5994a030-78ea-42c2-913a-1b2a9fcc2ea4.xml, _WWAN_SMS_SEND_PDU, netvista.wwan_sms_send_pdu, wwan/PWWAN_SMS_SEND_PDU, wwan/WWAN_SMS_SEND_PDU"
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
targetos: Windows
req.typenames: WWAN_SMS_SEND_PDU, *PWWAN_SMS_SEND_PDU
f1_keywords:
 - _WWAN_SMS_SEND_PDU
 - wwan/_WWAN_SMS_SEND_PDU
 - PWWAN_SMS_SEND_PDU
 - wwan/PWWAN_SMS_SEND_PDU
 - WWAN_SMS_SEND_PDU
 - wwan/WWAN_SMS_SEND_PDU
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_SMS_SEND_PDU
 - PWWAN_SMS_SEND_PDU
 - WWAN_SMS_SEND_PDU
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
     <a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_sms_send">WWAN_SMS_SEND</a> structure and their
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
     <a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_device_caps">WWAN_DEVICE_CAPS</a>), 
     <b>PduData</b> contains the SMS message as a byte array, as defined in section 3.4.2.1 SMS Point-to-Point
     Message in the 3GPP2 specification C.S0015-A "Short Message Service (SMS) for Wideband Spread Spectrum
     Systems". SMS will only support Wireless Messaging Teleservice (WMT) format. Miniport drivers should
     typecast this information to BYTE[] for CDMA-based devices. It is not coded in hexadecimal string
     format.

## -see-also

<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_sms_send">WWAN_SMS_SEND</a>

