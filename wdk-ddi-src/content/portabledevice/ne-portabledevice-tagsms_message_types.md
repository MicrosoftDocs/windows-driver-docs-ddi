---
UID: NE:portabledevice.tagSMS_MESSAGE_TYPES
title: tagSMS_MESSAGE_TYPES
author: windows-driver-content
description: The SMS_MESSAGE_TYPES enumeration type describes the content type of a short message service (SMS) message.
old-location: wpddk\sms_message_types.htm
tech.root: wpd_dk
ms.assetid: abb3da2b-30c0-44af-b80d-86580610681a
ms.date: 02/15/2018
ms.keywords: SMS_BINARY_MESSAGE, SMS_MESSAGE_TYPES, SMS_MESSAGE_TYPES enumeration, SMS_TEXT_MESSAGE, enumeration, portabledevice/SMS_BINARY_MESSAGE, portabledevice/SMS_MESSAGE_TYPES, portabledevice/SMS_TEXT_MESSAGE, tagSMS_MESSAGE_TYPES, wpddk.sms_message_types
ms.topic: enum
req.header: portabledevice.h
req.include-header: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	PortableDevice.h
api_name:
-	SMS_MESSAGE_TYPES
product:
-	Windows
targetos: Windows
req.typenames: SMS_MESSAGE_TYPES
---

# tagSMS_MESSAGE_TYPES enumeration


## -description



The <b>SMS_MESSAGE_TYPES</b> enumeration type describes the content type of a short message service (SMS) message.




## -enum-fields




### -field SMS_TEXT_MESSAGE

A text message.


### -field SMS_BINARY_MESSAGE

A binary message.


## -remarks



This enumeration is used by the <a href="https://msdn.microsoft.com/f69f4446-2d7c-4f33-b90c-535de169a4ec">WPD_COMMAND_SMS_SEND Command</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff597672">Structures and Enumeration Types</a>
 

 

