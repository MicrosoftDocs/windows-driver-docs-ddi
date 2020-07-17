---
UID: NS:wwan._WWAN_SMS_CDMA_RECORD
title: _WWAN_SMS_CDMA_RECORD (wwan.h)
description: The WWAN_SMS_CDMA_RECORD structure represents CDMA-based SMS text message records.
old-location: netvista\wwan_sms_cdma_record.htm
tech.root: netvista
ms.assetid: 4138be92-1f54-4478-8fbb-951f1d06cb66
ms.date: 05/02/2018
keywords: ["_WWAN_SMS_CDMA_RECORD structure"]
ms.keywords: "*PWWAN_SMS_CDMA_RECORD, PWWAN_SMS_CDMA_RECORD, PWWAN_SMS_CDMA_RECORD structure pointer [Network Drivers Starting with Windows Vista], WWAN_SMS_CDMA_RECORD, WWAN_SMS_CDMA_RECORD structure [Network Drivers Starting with Windows Vista], WwanRef_3356fcf9-99f2-4c07-89d5-fa73019f9a27.xml, _WWAN_SMS_CDMA_RECORD, netvista.wwan_sms_cdma_record, wwan/PWWAN_SMS_CDMA_RECORD, wwan/WWAN_SMS_CDMA_RECORD"
f1_keywords:
 - "wwan/WWAN_SMS_CDMA_RECORD"
 - "WWAN_SMS_CDMA_RECORD"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wwan.h
api_name:
- WWAN_SMS_CDMA_RECORD
product:
- Windows
targetos: Windows
req.typenames: WWAN_SMS_CDMA_RECORD, *PWWAN_SMS_CDMA_RECORD
---

# _WWAN_SMS_CDMA_RECORD structure


## -description


The WWAN_SMS_CDMA_RECORD structure represents CDMA-based SMS text message records.


## -struct-fields




### -field MessageIndex

An index into the virtual message store that is maintained by the miniport driver. This index is
     1-based and the maximum index is 
     <b>ulMaxMessageIndex</b> as returned in WWAN_SMS_CONFIGURATION_STATUS. Be aware that the specification
     does not differentiate between physically available data stores. If the message is a Class 0
     (flash/alert) message, this must be set to WWAN_MESSAGE_INDEX_NONE.


### -field MsgStatus

The status of the record that represents whether the SMS message is new (unread), old (read), a
     draft, or sent.


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
     <b>WwanMsgStatusDraft</b> or 
     <b>WwanMsgStatusSent</b>, miniport drivers should specify the receiver's mobile number in the previous
     members. Otherwise, if 
     <b>MsgStatus</b> is 
     <b>WwanMsgStatusNew</b> or 
     <b>WwanMsgStatusOld</b>, miniport drivers should specify the sender's mobile number.


### -field ScTimeStamp

A string that represent the Service Center (SC) timestamp, in the following format: "
      <i>YY</i>/<i>MM</i>/<i>DD</i>,
      <i>HH</i>:<i>mm</i>:<i>SS</i>±<i>ZZ</i>" where:

<ul>
<li>
<i>YY</i> represents the last two digits of the year. For example, 07 corresponds to 2007. Valid range
        is between 00 and 99.

</li>
<li>
<i>MM</i> represents the month index in double digits. For example, 01 for January and 12 corresponds
        to December. Valid range is between 01 and 12.

</li>
<li>
<i>DD</i> represents the day of the month in double digits. For example, 01 corresponds to the 1st day
        of the month, and 31 corresponds to the 31st day. Valid range is between 01 and 31.

</li>
<li>
<i>HH</i> represents the hours in 24-hour format. For example, 01 corresponds to 1 AM and 13
        corresponds to 1PM. Valid range is between 00 and 23.

</li>
<li>
<i>mm</i> represents the minutes in double digits. For example, 01 corresponds to 1 minute and 30
        corresponds to 30 minutes. Valid range is between 00 and 59.

</li>
<li>
<i>SS</i> represents the seconds in double digits. For example, 01 corresponds to 1 second and 30
        corresponds to 30 seconds. Valid range is between 00 and 59.

</li>
<li>
<i>ZZ</i> represents the time zone with reference to Greenwich Mean Time (GMT). For example, 01
        corresponds to 1 hour and 12 corresponds to 12 hours. Valid range is between 00 and 13 (-12 to +13
        when combined with the Â± symbol).

</li>
</ul>
For example, to represent October 2nd, 1996, 20:01:54 GMT+2 hours use the following string timestamp
      "96/10/02,20:01:54+02"


### -field EncodingId

The encoding that is used in the CDMA message. 
     <b>EncodedMsg</b> message should be interpreted based on the value of this member.


### -field LanguageId

The language that is used in the SMS text message.


### -field SizeInBytes

The size, in bytes, of 
     <b>EncodedMsg</b> . The encoded message can have a maximum length of WWAN_SMS_CDMA_MAX_BUF_LEN. Miniport
     drivers must specify a value for this member for all encoding types.


### -field SizeInCharacters

Size of 
     <b>EncodedMsg</b> in number of characters represented by the encoded data. Miniport drivers should
     specify 0 for this member when 
     <b>EncodingId</b> is set to 
     <b>WwanSmsCdmaEncodingShiftJis</b> or 
     <b>WwanSmsCdmaEncodingKorean</b>.


### -field EncodedMsg

The encoded content of the record that represents the SMS text message.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ne-wwan-_wwan_msg_status">WWAN_MSG_STATUS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ne-wwan-_wwan_sms_cdma_encoding">WWAN_SMS_CDMA_ENCODING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ne-wwan-_wwan_sms_cdma_lang">WWAN_SMS_CDMA_LANG</a>
 

 

