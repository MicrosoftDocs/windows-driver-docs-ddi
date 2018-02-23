---
UID: NS:wwan._WWAN_SMS_CDMA_RECORD
title: "_WWAN_SMS_CDMA_RECORD"
author: windows-driver-content
description: The WWAN_SMS_CDMA_RECORD structure represents CDMA-based SMS text message records.
old-location: netvista\wwan_sms_cdma_record.htm
old-project: netvista
ms.assetid: 4138be92-1f54-4478-8fbb-951f1d06cb66
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PWWAN_SMS_CDMA_RECORD, PWWAN_SMS_CDMA_RECORD, netvista.wwan_sms_cdma_record, WWAN_SMS_CDMA_RECORD, WwanRef_3356fcf9-99f2-4c07-89d5-fa73019f9a27.xml, PWWAN_SMS_CDMA_RECORD structure pointer [Network Drivers Starting with Windows Vista], wwan/PWWAN_SMS_CDMA_RECORD, WWAN_SMS_CDMA_RECORD structure [Network Drivers Starting with Windows Vista], wwan/WWAN_SMS_CDMA_RECORD, _WWAN_SMS_CDMA_RECORD"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wwan.h
apiname:
-	WWAN_SMS_CDMA_RECORD
product: Windows
targetos: Windows
req.typenames: WWAN_SMS_CDMA_RECORD, *PWWAN_SMS_CDMA_RECORD
req.product: Windows 10 or later.
---

# _WWAN_SMS_CDMA_RECORD structure


## -description


The WWAN_SMS_CDMA_RECORD structure represents CDMA-based SMS text message records.


## -syntax


````
typedef struct _WWAN_SMS_CDMA_RECORD {
  ULONG                  MessageIndex;
  WWAN_MSG_STATUS        MsgStatus;
  CHAR                   Address[WWAN_SMS_CDMA_ADDR_MAX_LEN];
  CHAR                   ScTimeStamp[WWAN_SMS_CDMA_TIMESTAMP_MAX_LEN];
  WWAN_SMS_CDMA_ENCODING EncodingId;
  WWAN_SMS_CDMA_LANG     LanguageId;
  USHORT                 SizeInBytes;
  BYTE                   SizeInCharacters;
  BYTE                   EncodedMsg[WWAN_SMS_CDMA_MAX_BUF_LEN];
} WWAN_SMS_CDMA_RECORD, *PWWAN_SMS_CDMA_RECORD;
````


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
"+ &lt;International Country Code&gt; &lt;Mobile Number&gt;\0"

</li>
<li>
"&lt;Mobile Number&gt;\0"

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

<a href="..\wwan\ne-wwan-_wwan_msg_status.md">WWAN_MSG_STATUS</a>



<a href="..\wwan\ne-wwan-_wwan_sms_cdma_encoding.md">WWAN_SMS_CDMA_ENCODING</a>



<a href="..\wwan\ne-wwan-_wwan_sms_cdma_lang.md">WWAN_SMS_CDMA_LANG</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_SMS_CDMA_RECORD structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

