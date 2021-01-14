---
UID: NS:wwan._WWAN_SMS_SEND_CDMA
title: _WWAN_SMS_SEND_CDMA (wwan.h)
description: The WWAN_SMS_SEND_CDMA structure represents a CDMA-based SMS text message to send.
old-location: netvista\wwan_sms_send_cdma.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["WWAN_SMS_SEND_CDMA structure"]
ms.keywords: "*PWWAN_SMS_SEND_CDMA, PWWAN_SMS_SEND_CDMA, PWWAN_SMS_SEND_CDMA structure pointer [Network Drivers Starting with Windows Vista], WWAN_SMS_SEND_CDMA, WWAN_SMS_SEND_CDMA structure [Network Drivers Starting with Windows Vista], WwanRef_0b4ec978-8685-46a6-b1dd-556606660614.xml, _WWAN_SMS_SEND_CDMA, netvista.wwan_sms_send_cdma, wwan/PWWAN_SMS_SEND_CDMA, wwan/WWAN_SMS_SEND_CDMA"
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
req.typenames: WWAN_SMS_SEND_CDMA, *PWWAN_SMS_SEND_CDMA
f1_keywords:
 - _WWAN_SMS_SEND_CDMA
 - wwan/_WWAN_SMS_SEND_CDMA
 - PWWAN_SMS_SEND_CDMA
 - wwan/PWWAN_SMS_SEND_CDMA
 - WWAN_SMS_SEND_CDMA
 - wwan/WWAN_SMS_SEND_CDMA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_SMS_SEND_CDMA
 - PWWAN_SMS_SEND_CDMA
 - WWAN_SMS_SEND_CDMA
---

# _WWAN_SMS_SEND_CDMA structure


## -description

The WWAN_SMS_SEND_CDMA structure represents a CDMA-based SMS text message to send.

## -struct-fields

### -field EncodingId

The encoding that is used in the CDMA message. 
     <b>EncodedMsg</b> message should be interpreted based on the value of this member.

### -field LanguageId

The language used in CDMA message. This is an indicator of the language used in SMS message and
     may be set to 
     <b>WwanSmsCdmaLangUnknown</b>, if the language is not known.

### -field Address

A NULL-terminated string with a maximum length of 15 digits that represents a mobile number. The
     number can be in any of the following formats:
     

<ul>
<li>
"+ <International Country Code> <Mobile Number>\0"

</li>
<li>
"<Mobile Number>\0"

</li>
</ul>
If 
     <b>MsgStatus</b> is 
     <i>WwanMsgStatusDraft</i> or 
     <i>WwanMsgStatusSent</i>, miniport drivers should specify the receiver's mobile number in the previous
     members. Otherwise, if 
     <b>MsgStatus</b> is 
     <i>WwanMsgStatusNew</i> or 
     <i>WwanMsgStatusOld</i>, miniport drivers should specify the sender's mobile number.

### -field SizeInBytes

The size, in bytes, of 
     <b>EncodedMsg</b> . The encoded message can have a maximum length of WWAN_SMS_CDMA_MAX_BUF_LEN. Miniport
     drivers must specify a value for this member for all encoding types.

### -field SizeInCharacters

Size of 
     <b>EncodedMsg</b> in number of characters represented by the encoded data. Miniport drivers should
     specify 0 for this member when 
     <b>EncodingId</b> is set to 
     <i>WwanSmsCdmaEncodingShiftJis</i> or 
     <i>WwanSmsCdmaEncodingKorean</i>.

### -field EncodedMsg

The encoded content that represents the CDMA-based SMS text message.

## -see-also

<a href="/windows-hardware/drivers/ddi/wwan/ne-wwan-_wwan_sms_cdma_encoding">WWAN_SMS_CDMA_ENCODING</a>



<a href="/windows-hardware/drivers/ddi/wwan/ne-wwan-_wwan_sms_cdma_lang">WWAN_SMS_CDMA_LANG</a>



<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_sms_send">WWAN_SMS_SEND</a>

