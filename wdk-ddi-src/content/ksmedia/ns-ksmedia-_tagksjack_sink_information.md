---
UID: NS:ksmedia._tagKSJACK_SINK_INFORMATION
title: "_tagKSJACK_SINK_INFORMATION"
author: windows-driver-content
description: The KSJACK_SINK_INFORMATION structure specifies information about a display-related digital audio device, such as an HDMI device or a display port.
old-location: audio\ksjack_sink_information.htm
old-project: audio
ms.assetid: ec832068-9b5d-40ce-bafc-31642539e2d9
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: "*PKSJACK_SINK_INFORMATION, PKSJACK_SINK_INFORMATION, ksmedia/PKSJACK_SINK_INFORMATION, audio.ksjack_sink_information, ksmedia/KSJACK_SINK_INFORMATION, _tagKSJACK_SINK_INFORMATION, aud-prop_e9bbfa8a-d002-400c-a35d-3da0a8026cd6.xml, PKSJACK_SINK_INFORMATION structure pointer [Audio Devices], KSJACK_SINK_INFORMATION, KSJACK_SINK_INFORMATION structure [Audio Devices]"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later Windows operating systems.
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
-	ksmedia.h
apiname:
-	KSJACK_SINK_INFORMATION
product: Windows
targetos: Windows
req.typenames: KSJACK_SINK_INFORMATION, *PKSJACK_SINK_INFORMATION
---

# _tagKSJACK_SINK_INFORMATION structure


## -description


The <code>KSJACK_SINK_INFORMATION</code> structure specifies information about a display-related digital audio device, such as an HDMI device or a display port.


## -syntax


````
typedef struct _tagKSJACK_SINK_INFORMATION {
  KSJACK_SINK_CONNECTIONTYPE ConnType;
  WORD                       ManufacturerId;
  WORD                       ProductId;
  WORD                       AudioLatency;
  BOOL                       HDCPCapable;
  BOOL                       AICapable;
  UCHAR                      SinkDescriptionLength;
  WCHAR                      SinkDescription[MAX_SINK_DESCRIPTION_NAME_LENGTH];
  LUID                       Reserved;
} KSJACK_SINK_INFORMATION, *PKSJACK_SINK_INFORMATION;
````


## -struct-fields




#### - ConnType

Specifies the connection type of the sink. This parameter is an enumeration of type <a href="http://go.microsoft.com/fwlink/p/?linkid=143848">KSJACK_SINK_CONNECTIONTYPE</a>. 


#### - ManufacturerId

Specifies the sink manufacturer ID.


#### - ProductId

Specifies the sink product ID.


#### - AudioLatency

Specifies the sink audio latency.


#### - HDCPCapable

Specifies that this jack sink provides support for High-bandwidth Digital Content Protection (HDCP).


#### - AICapable

Specifies that this jack sink provides support for the following data packet types: audio content protection (ACP), international standard recording code-1 (ISRC1), and ISRC2.


#### - SinkDescriptionLength

Specifies the length of the <b>SinkDescription</b>[] member.


#### - SinkDescription

Specifies a string that contains the sink name, which must be NULL-terminated. The maximum length is defined by the MAX_SINK_DESCRIPTION_NAME_LENGTH constant (31  characters, plus a terminating <b>NULL</b>).


### -field PortId

 



#### - Reserved

Reserved.


## -see-also

<a href="..\igpupvdev\ns-igpupvdev-_luid.md">LUID</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSJACK_SINK_INFORMATION structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

