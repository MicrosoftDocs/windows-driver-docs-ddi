---
UID: NS:wwan._WWAN_SMS_SEND
title: _WWAN_SMS_SEND (wwan.h)
description: The WWAN_SMS_SEND structure represents an SMS text message to send.
old-location: netvista\wwan_sms_send.htm
tech.root: netvista
ms.assetid: 2d2e5d13-56ca-452c-86fd-4a48b11d53ab
ms.date: 05/02/2018
keywords: ["WWAN_SMS_SEND structure"]
ms.keywords: "*PWWAN_SMS_SEND, PWWAN_SMS_SEND, PWWAN_SMS_SEND structure pointer [Network Drivers Starting with Windows Vista], WWAN_SMS_SEND, WWAN_SMS_SEND structure [Network Drivers Starting with Windows Vista], WwanRef_5212cb88-8eeb-4aef-8ecd-8a0634db962c.xml, _WWAN_SMS_SEND, netvista.wwan_sms_send, wwan/PWWAN_SMS_SEND, wwan/WWAN_SMS_SEND"
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
req.typenames: WWAN_SMS_SEND, *PWWAN_SMS_SEND
f1_keywords:
 - _WWAN_SMS_SEND
 - wwan/_WWAN_SMS_SEND
 - PWWAN_SMS_SEND
 - wwan/PWWAN_SMS_SEND
 - WWAN_SMS_SEND
 - wwan/WWAN_SMS_SEND
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - WWAN_SMS_SEND
---

# _WWAN_SMS_SEND structure


## -description

The WWAN_SMS_SEND structure represents an SMS text message to send.

## -struct-fields

### -field SmsFormat

The format of the SMS text message.

### -field u

Container union for the different SMS formats.

### -field u.Pdu

Short message data types to be used depending on the value of 
      <b>SmsFormat</b> as shown in the following table.
      

<table>
<tr>
<th>SmsFormat</th>
<th>Member to use</th>
</tr>
<tr>
<td>
WwanSmsFormatPdu

</td>
<td>
Pdu

</td>
</tr>
<tr>
<td>
WwanSmsFormatCdma

</td>
<td>
Cdma

</td>
</tr>
</table>

### -field u.Cdma

Short message data types to be used depending on the value of 
      <b>SmsFormat</b> as shown in the following table.
      

<table>
<tr>
<th>SmsFormat</th>
<th>Member to use</th>
</tr>
<tr>
<td>
WwanSmsFormatPdu

</td>
<td>
Pdu

</td>
</tr>
<tr>
<td>
WwanSmsFormatCdma

</td>
<td>
Cdma

</td>
</tr>
</table>

## -see-also

<a href="/windows-hardware/drivers/ddi/ndiswwan/ns-ndiswwan-_ndis_wwan_sms_send">NDIS_WWAN_SMS_SEND</a>



<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_sms_send_cdma">WWAN_SMS_SEND_CDMA</a>



<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_sms_send_pdu">WWAN_SMS_SEND_PDU</a>