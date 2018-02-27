---
UID: NS:wwan._WWAN_SMS_PDU_RECORD
title: "_WWAN_SMS_PDU_RECORD"
author: windows-driver-content
description: The WWAN_SMS_PDU_RECORD structure represents a PDU-style SMS message record.
old-location: netvista\wwan_sms_pdu_record.htm
old-project: netvista
ms.assetid: 20200222-8539-497e-891e-2d29c3207c56
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PWWAN_SMS_PDU_RECORD, PWWAN_SMS_PDU_RECORD, PWWAN_SMS_PDU_RECORD structure pointer [Network Drivers Starting with Windows Vista], WWAN_SMS_PDU_RECORD, WWAN_SMS_PDU_RECORD structure [Network Drivers Starting with Windows Vista], WwanRef_b21c5d84-e8d4-4cf4-9942-f6f1a14c23c0.xml, _WWAN_SMS_PDU_RECORD, netvista.wwan_sms_pdu_record, wwan/PWWAN_SMS_PDU_RECORD, wwan/WWAN_SMS_PDU_RECORD"
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
-	WWAN_SMS_PDU_RECORD
product: Windows
targetos: Windows
req.typenames: WWAN_SMS_PDU_RECORD, *PWWAN_SMS_PDU_RECORD
req.product: Windows 10 or later.
---

# _WWAN_SMS_PDU_RECORD structure


## -description


The WWAN_SMS_PDU_RECORD structure represents a PDU-style SMS message record.


## -syntax


````
typedef struct _WWAN_SMS_PDU_RECORD {
  ULONG           MessageIndex;
  WWAN_MSG_STATUS MsgStatus;
  BYTE            Size;
  CHAR            PduData[WWAN_SMS_PDU_HEX_BUF_LEN];
} WWAN_SMS_PDU_RECORD, *PWWAN_SMS_PDU_RECORD;
````


## -struct-fields




### -field MessageIndex

An index into the virtual message store that is maintained by the miniport driver. This index is
     1-based and the maximum index is 
     <b>ulMaxMessageIndex</b> returned in WWAN_SMS_CONFIGURATION_STATUS. Be aware that the specification does
     not differentiate between physically available data stores. If the message is a Class 0 (flash/alert)
     message, this must be set to WWAN_MESSAGE_INDEX_NONE.


### -field MsgStatus

The status of the record that represents whether the SMS message is new (unread), old (read), a
     draft, or sent.


### -field Size

The size, in bytes, of the record.
     

For GSM-based devices, this represents the size of the message before conversion to a hexadecimal
     string.

For CDMA-based devices, this represents the number of bytes in the 
     <b>PduData</b> .


### -field PduData

For GSM-based devices, a NULL-terminated string that contains the content of the record coded in a
     hexadecimal string format (according to the 3GPP TS 27.005 and 3GPP TS 23.040 standards) that represents
     the SMS message. 
     

For CDMA-based devices that support reading SMS messages in binary format (as returned in
     WWAN_SMS_CAPS as WWAN_SMS_CAPS_PDU_RECEIVE) this member contains the SMS message as a byte array, as
     defined in section 3.4.2.1 SMS Point-to-Point Message in 3GPP2 specification C.S0015-A "Short Message
     Service (SMS) for Wideband Spread Spectrum Systems". SMS will only support Wireless Messaging
     Teleservice (WMT) format. Miniport drivers should typecast this information to BYTE[] for CDMA-based
     devices. It is not coded in hexadecimal string format. The message is not NULL-terminated.


## -see-also

<a href="..\wwan\ne-wwan-_wwan_msg_status.md">WWAN_MSG_STATUS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_SMS_PDU_RECORD structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

